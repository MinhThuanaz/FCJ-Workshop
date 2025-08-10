---
title : "Creating CloudFront Distributions for S3 static web"
date: 2024-06-18

weight : 1
chapter : false
pre : " <b> 2.1.1 </b> "
---

## Creating CloudFront distribution

### Open CloudFront service
- In the AWS Management Console, find **CloudFront** → **Create Distribution**.

### Specify Origin
- **Origin type**: Select **Amazon S3**.
- **Origin domain**: Select the created Bucket S3.
- If the bucket has enabled the website Hosting website → press **Use website endpoint** so that CloudFront serves the correct index.html file.
- **Allow Private S3 Bucket Access to CloudFront**: Turn over if you want to limit access to only via CloudFront.

### Cache & Security configuration
- **Viewer Protocol Policy**: Redirect http to https.
- **Default Root Object**: `Index.html`.

### skip the Enable Security step if you want to save money
- In step **Enable Security (WAF)**:
  - Select **Do not Enable Security Protections** to not attach WAF.
  - Later, go to the AWS WAF Console to attach WebaCl when tested.

### Create a distribution
- Press **Create Distribution**.
- Wait for the state **deployed**.
