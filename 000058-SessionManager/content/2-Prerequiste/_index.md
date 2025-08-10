---
title : "Preparation "
date: 2024-06-18

weight : 2
chapter : false
pre : " <b> 2. </b> "
---


In this section, you will create a demo environment to be ready to deploy smart WAF, including:
- **Sample web application** for WAF to protect (S3 or EC2).
- **AWS WAF Webacl** to block dangerous access.
- **Cloudwatch Log Group** to record security events from WAF

To learn how to create EC2, S3, ... you can refer to the Lab:
  - [Introduction to Amazon EC2](https://000004.awsstudygroup.com/vi/)
  - [Working with Amazon S3](https://000057.awsstudygroup.com/vi/)
  - [Working with Amazon WAF](https://000026.awsstudygroup.com/vi/)
  - [Introduction to Amazon Lambda](https://000022.awsstudygroup.com/vi/)


### Content
  - [Creating S3 Static Website](2.1-createwebsample/)
  - [Create WAF WebaCl and assign to Resource](2.2-createWAFwebacl/)
  - [Turn on logging and create Log Group](2.3-turnonloggingcreateLogGroup/)