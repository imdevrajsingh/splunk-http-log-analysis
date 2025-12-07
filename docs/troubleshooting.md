# Troubleshooting Guide

1. Dashboard shows "No Results"
   → Fix: Set Time Range to All Time

2. Fields not appearing
   → Fix: Use sourcetype=_json during ingestion

3. Panels show data but dashboard doesn’t
   → Fix: Permissions → Set Dashboard to read for Everyone

4. Searches work but dashboard empty
   → Fix: Panel search inherits different timepicker → set to "Use Dashboard Time"
