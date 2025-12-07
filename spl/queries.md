# SPL Queries Used in All 7 Dashboards

---

## 1. Sensitive File Access Attempts
index=httplogs (uri="/etc/passwd" OR uri="/shell.php" OR uri="/admin" OR uri="/phpmyadmin" OR uri="/config.php")
| table _time id.orig_h method uri status_code user_agent resp_body_len
| sort - _time

---

## 2. Suspicious User Agents
index=httplogs user_agent IN ("*sqlmap*","*curl*","*python*","*botnet*")
| stats count BY user_agent, id.orig_h, uri
| sort - count

---

## 3. Large Data Transfer Detection
index=httplogs
| where isnum(resp_body_len)
| sort - resp_body_len
| table _time id.orig_h id.resp_h uri resp_body_len status_code user_agent

---

## 4. Uncommon HTTP Methods
index=httplogs NOT method IN ("GET","POST")
| stats count BY method, id.orig_h
| sort - count

---

## 5. Suspicious Admin Paths
index=httplogs (uri="/phpmyadmin" OR uri="/wp-admin" OR uri="/config.php" OR uri="/shell.php" OR uri="/admin")
| stats count BY uri, id.orig_h, user_agent
| sort - count

---

## 6. Error Rate / Status Code Analysis
index=httplogs status_code>=400
| eval class = if(status_code >=500,"5xx","4xx")
| stats count BY class, status_code, uri
| sort - count

---

## 7. Top Suspicious Source Hosts
index=httplogs (user_agent IN ("*sqlmap*","*curl*","*python*","*botnet*")
 OR uri IN ("/etc/passwd","/shell.php","/admin","/phpmyadmin","/config.php")
 OR resp_body_len>1000000)
| stats count AS events, dc(uri) AS unique_uris, sum(resp_body_len) AS total_bytes BY id.orig_h
| sort - events
