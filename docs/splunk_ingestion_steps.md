# Splunk Log Ingestion Steps

1. Open Splunk Web: http://localhost:8000/
2. Go to Settings → Add Data
3. Choose "Upload"
4. Select the file: data/http_logs.json
5. Click Next
6. Set Source Type to: _json
7. Create new index: httplogs
8. Finish
9. Validate using:

index=httplogs | head 10
