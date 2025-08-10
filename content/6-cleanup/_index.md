+++
title = "Clean up resources"
date = 2022
weight = 6
chapter = false
pre = "<b>6. </b>"
+++



#### Delete S3 bucket

1. Go to [S3 service management console](https://s3.console.aws.amazon.com/s3/home)
   + Click on the S3 bucket we created
   + Click **Empty**.
   + Enter **permanently delete**, then click **Empty** to proceed to delete the object in the bucket.
   + Click **Exit**.

2. After deleting all objects in the bucket, click **Delete**

3. Enter the name of the S3 bucket, then click **Delete bucket** to proceed with deleting the S3 bucket.


#### Delete Web ACLs
- Go to [WAF & SHIELD Management Console](https://us-east-1.console.aws.amazon.com/wafv2/homev2/start?region=global)
   + Click **WebACLs** and choose webacls we created
   + Click **Delete**, enter delete to confirm deleting the WebACL (you must **Disassociate** it from CloudFront before it can be deleted).


#### Delete Log Group CloudWatch
- Select the created log groups
- Click the **Actions** menu
- Select **delete log group(s)**
- Confirm Delete


#### Delete Lambda
- Go to [Lambda Management Console](https://us-east-1.console.aws.amazon.com/lambda/home?region=us-east-1#/discover)
   + Click on **Functions** 
   + Click function we created 
   + Click **Actions**
   + Choose **delete**
   + Fill **confirm** to confirm for deleting


#### Delete ClouFront Distribution
- Go to [CloudFront Management Console](https://us-east-1.console.aws.amazon.com/cloudfront/v4/home?region=us-east-1#/distributions)
   + Click on **Distributions** menu
   + Click on distribution created
   + Click **Disable** (Must be disabled before delete distribution)
   + Click **Delete**