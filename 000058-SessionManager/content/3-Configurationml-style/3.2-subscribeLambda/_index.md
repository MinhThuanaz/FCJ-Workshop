---
title : "Subscribe Lambda with log group"
date: 2024-06-18

weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---


- Through this access link to return to Cloudwatch Console page: [CloudWatch Console](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#logsV2:log-groups)
- Find log group that you configured in the previous step for waf
  ![ConnectPrivate](/images/3.connect/pic10.png)

- Select Log Group → Actions → Create Subscribe Filter.
  ![ConnectPrivate](/images/3.connect/pic11.png)

- Choose the following items including:
  - Destination: **Lambda Function**
  -Lambda: `WAF-ML-DETACTION`
  -Name Subscribe Filter Name: `Waf-Logs-to-Lambda`
- Filter Pattern: Leave empty (means send all log).
- Confirm and create success.
  ![ConnectPrivate](/images/3.connect/pic12.png)