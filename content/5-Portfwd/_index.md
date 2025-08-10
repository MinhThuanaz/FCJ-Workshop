---
title : "Test & Validation"
date: 2024-06-18 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

### Target
- Check out **Rate Limited Rule** and **Geo-Blocking Rule** have worked as designed.
- Make sure not to affect users.

---

### CONCEPTS RATE LIMITING RULE
1. Use the tool `ab` (Apache Benchmark) or `hey` to send **3000 request** within **5 minutes** to endpoint `/API/Login`.
2. Expect:
   - Request exceeds 2000/5 minutes from the same IP will be **match rule** and log log.
   - Because in the `Count` mode, the request is still returned but will see the log match in Cloudwatch.



### In case of Geo-Blocking Rule test
1. Use VPN to choose IP from the country in the block list (Example: `RU`).
2. Send Request to the homepage or endpoint `/api/data`.
3. Expected:
   - Request from IP of that country will be Match Geo-Blocking Rule and write log.
   - In the `Count` mode, there is still a response but an entry log.