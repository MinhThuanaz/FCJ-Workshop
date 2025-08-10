---
title : "Create WAF WebaCl and assign to Resource"
date: 2024-06-18

weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Create a WebACL

- Back to the AWS Console homepage and open **AWS WAF** Console
  ![Connectprivate] (/images/2.prerequisite/pic14.png)
- Next, select **WebACls** and click **Create Webacl**
  ![Connectprivate] (/images/2.prerequisite/pic13.png)


-WebACL name: Example: ML-WAF-DEMO.
- **Add AWS Resources** → Select Resource you want to protect (select CloudFront Distribution that we have created earlier).
- Rules: temporarily leave empty (will add in the next step).
- Default Action: Allow.
- Complete WebACL creation.
  ! [Connectprivate] (/images/2.prerequisite/pic15.png)

  ! [Connectprivate] (/images/2.prerequisite/pic16.png)

  ! [Connectprivate] (/images/2.prerequisite/pic17.png)