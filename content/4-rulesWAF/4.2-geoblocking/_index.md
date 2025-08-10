---
title : "Setting Geo-Blocking Rule"
date: 2024-06-18

weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---

### Target
- Limit or block access from high -risk countries/territories not to serve the market.

### Set on AWS Console
1. In WebaCl, select **Add Rules** → **Add My Own Rules and Rule Groups**.
2. Name Rule: `Geoblock-Highrisk`.
3. Select **geo match**.
4. Add Country Codes to Block: Example `[" ru "," CN "," KP "]` `.
5. If you need a valid Whitelist IP from this country, create IPSet Whitelist and use not statement.
6. Action: **Count** to monitor.
7. Enable Cloudwatch Metrics and Sampled Requests.
8. Save and Deploy.