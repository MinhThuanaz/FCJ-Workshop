---
title : "Setting Rate Limiting Rule"
date: 2024-06-18

weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

### Target
- Limit the number of requests from the same IP over a certain period of time to reduce the load and prevent the attack of Brute-Force or BOT Traffic.

### Set on AWS Console
1. Go **AWS WAF & Shield** in AWS Management Console.
2. Select **WebaCl** that you want to add rule.
3. Select **Add rules** → **Add my own rules and rule groups**.
4. Name Rule: `Ratelimit-Api`.
5. Select **Rate-based Rule**.
6. Configuration:
   - Limited: `2000` Requests / 5 minutes / IP.
   - Aggregate key: `ip`.
   - Scope-down: Applies to Uri Path `/API/` `/Login`.
7. Action: **Count** for monitoring before blocking.
8. Enable Cloudwatch Metrics and Sampled Requests.
9. Save and Deploy.