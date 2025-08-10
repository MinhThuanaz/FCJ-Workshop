---
title : "Create Lambda Function check the log waf"
date: 2024-06-18

weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

### Target:
- Lambda will receive logs from WAF (Cloudwatch Logs or Kinesis), analysis and detect signs of attack based on custom logic or rule.

### started
- Go to Lambda Console: Access [AWS Lambda Console] (https://console.aws.amazon.com/lambda/home?region=us-East-1)
- Click **Create A Function**
  ! [Connectprivate] (/images/3.Connect/pic01.png)

- After displaying, select creating methods including:
  - Author from scratch
  - Function name: `waf-ml-detection`
  - Runtime: Python 3.10 (hoặc Node.js)
  - Architecture: x86_64
  - Permissions:
    - Choose **Create a new role with basic Lambda permissions**.
  - Choose **Create function**
  ![ConnectPrivate](/images/3.connect/pic02.png)
  ![ConnectPrivate](/images/3.connect/pic03.png)