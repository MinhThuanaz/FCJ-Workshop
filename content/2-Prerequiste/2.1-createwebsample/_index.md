---
title : "Creating S3 Static Website"
date: 2024-06-18

weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---


### Starting S3 Bucket
- Access **AWS Management Console**
- Log in with your account.
- After logging in, you will transfer users to the main page of AWS Manage Console as shown:
  
  ![ConnectPrivate](/images/2.prerequisite/pic01.png) 

- Find and open services **S3**.

  ![ConnectPrivate](/images/2.prerequisite/pic02.png)
  ![ConnectPrivate](/images/2.prerequisite/pic03.png)

- Press **Create Bucket** at the homepage and fill out the following information:
  ! [ConnectPrivate] (/images/2.prerequisite/pic04.png)
  
  |                                                               |
  |------------------------|--------------------------------------|
  | **AWS Region**         | Choose the same Region with WAF (e.g. ` US-EAST-1`)|
  | **Bucket name**        | `waf-demo-yourname`                  |

  ![ConnectPrivate](/images/2.prerequisite/pic05.png)

- In the section **Object Ownership**, we choose **ACLs disabled (recommended)**.

  ![ConnectPrivate](/images/2.prerequisite/pic06.png)

- Next, In section **Block Public Access settings**:
  - Uncheck **Block all public access**.
  - Check **I acknowledge that the current settings might result in this bucket and the objects within becoming public**.

  ![ConnectPrivate](/images/2.prerequisite/pic07.png)

- Keep the same default settings, then press **Create Bucket**.

---

### Upload file `INDEX.HTML`
- Create file `INDEX.HTML` with basic content:
```html
<! Doctype html>
<html>
<btle> WAF Demo </title> </head>
<body> <h1> Hello waf! </h1> </body>
</tml>
````

- Access the newest created bucket → Click Upload.
  ![ConnectPrivate](/images/2.prerequisite/pic08.png)

  ![ConnectPrivate](/images/2.prerequisite/pic09.png)

- Select the file index.html and click Upload.
  ![ConnectPrivate](/images/2.prerequisite/pic10.png)

---

### Turn on Static Website Hosting
- In the bucket, open the tab ** Properties **
- Roll down to the website Hosting website → press ** edit **.
- Select ** Enable **.
- In the hosting section, select Host A Static website.
- INDEX Document: Enter `index.html`.
- Click Save Changes.
- Copy the endpoint URL displayed.

  ![ConnectPrivate](/images/2.prerequisite/pic11.png)

---

### Granting public access
- Go to Bucket's Permissions tab.
- Roll down at the **Bucket Policy**, click Edit and paste the following policy, change <Your-Bucket-name> by your bucket name:
```JSON
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadgetobject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "S3: Getobject",
      "Resource": "RNA: AWS: S3 ::: <Your-Bucket-name>/*" "
    }
  ]
}
````

- Press Save changes.
  ![ConnectPrivate](/images/2.prerequisite/pic12.png)

- Check access: Return the browser via **Endpoint URL** that you have created earlier, if you see the content "Hello waf!" Means you have succeeded.