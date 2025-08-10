---
title : "Turn on logging and create Log Group"
date: 2024-06-18

weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

### Target:
Record log request to Cloudwatch Logs so that later use ML analysis model.

- Go back to AWS WAF Console → WebACls
- Select the webacl you just created.

  ![ConnectPrivate](/images/2.prerequisite/pic18.png)

- After showing the webaCl information that you have created the item **logging and metrics**
- Select **Enable** in the right corner
- Select **Logging Destination**

  ![ConnectPrivate](/images/2.prerequisite/pic19.png)

- Select **Cloudwatch logs** (most popular)
  ! [Connectprivate] (/images/2.prerequisite/pic20.png)

- If there is no log group:
    + Open a new tab into Cloudwatch → Log Groups → Create Log Group.
    + Name (for example:/AWS/WAF/ML-WAF-Logs).
  ! [Connectprivate] (/images/2.prerequisite/pic21.png)

    + Back to the WAF screen, select Log Group just created.
    + Click **Save** and you have successfully enabled logging
  ! [Connectprivate] (/images/2.prerequisite/pic22.png)