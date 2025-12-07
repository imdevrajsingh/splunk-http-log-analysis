# Splunk HTTP Log Analysis Project (7 Security Dashboards)

This project showcases my complete end-to-end analysis of HTTP logs in Splunk, where I built **seven SOC-focused security dashboards**.  
The objective of this project is to detect malicious activities such as sensitive file access attempts, scanning, data exfiltration, enumeration, and abnormal web behavior.

This project demonstrates my hands-on experience with:
- Log ingestion in Splunk
- Writing SPL queries
- Building dashboards
- Investigating suspicious web traffic
- Detecting attacker behavior using HTTP logs

---

## 📌 Project Overview

This repository contains everything required to reproduce my Splunk project:

✔ Raw HTTP log dataset  
✔ All SPL queries  
✔ All 7 Splunk dashboards (exported XML)  
✔ Step-by-step documentation  
✔ Dashboard creation instructions  
✔ Troubleshooting guide  

This project is fully reproducible by anyone following the provided documentation.

---

## 📊 Dashboards Included (7 Total)

1. **Sensitive File Access Attempts Dashboard**  
2. **Suspicious User Agents Dashboard**  
3. **Large Data Transfer Detection Dashboard**  
4. **Uncommon / Suspicious HTTP Methods Dashboard**  
5. **Suspicious Admin & Hidden Paths Dashboard**  
6. **Error Rate / Status Code Analysis Dashboard**  
7. **Top Suspicious Source Hosts Dashboard**

These dashboards help detect:
- LFI attempts  
- Reconnaissance & scanning  
- Bot/Crawler activity  
- Misuse of uncommon methods  
- Web shell attempts  
- Data exfiltration  
- Abnormal traffic patterns  

---

## 📂 Repository Structure

splunk-http-log-analysis/
│
├── README.md
├── data/
│ └── http_logs.json
│
├── dashboards/
│ ├── sensitive_file_access_attempts.xml
│ ├── suspicious_user_agents.xml
│ ├── large_transfer_detection.xml
│ ├── uncommon_http_methods.xml
│ ├── suspicious_admin_paths.xml
│ ├── error_rate_analysis.xml
│ └── top_suspicious_hosts.xml
│
├── spl/
│ └── queries.md
│
└── docs/
├── splunk_ingestion_steps.md
├── dashboard_creation_steps.md
├── exporting_dashboards.md
└── troubleshooting.md


Each folder and file has a specific purpose to help others understand and reproduce the project easily.

---

## 🧪 Dataset Used

The dataset (`http_logs.json`) contains HTTP request records such as:
- HTTP method  
- URL/URI requested  
- User agent  
- Status codes  
- Response sizes  
- Source/Destination IPs  
- Event types  
- Timestamps  

This dataset helped me analyze:
- Recon activity  
- Errors  
- Admin page probes  
- Large transfers  
- Suspicious requests  
- Malicious tools like sqlmap, curl, python scripts, botnet scanners  

---

## 🛠 How to Reproduce This Project

All instructions are included in `/docs/`, including:

- **How to upload logs into Splunk**  
- **How to choose correct sourcetype (`_json`)**  
- **How to create index (httplogs)**  
- **How to write the SPL queries**  
- **How to build each dashboard panel**  
- **How to import/export dashboard XML files**  

Follow the docs and you will get the exact dashboards I created.

---

## 📁 Dashboard XML Files

All 7 dashboards built in Splunk are exported and stored in the `/dashboards/` folder.  
They can be imported using:

**Splunk → Dashboards → Import → Upload XML**

This instantly recreates my dashboards on any machine.

---

## 🎯 Skills Demonstrated

This project helped me develop:

### ✔ Splunk Log Ingestion  
### ✔ SPL Query Writing  
### ✔ Creating SOC-focused dashboards  
### ✔ Web attack pattern recognition  
### ✔ Threat detection using logs  
### ✔ Incident investigation approach  
### ✔ Identifying attacker TTPs  

---

## 🙌 Author

**Devraj Singh Kholiya**  
Aspiring SOC Analyst 
Delhi, India

---

## ⭐ If you like this project, feel free to star the repo!

