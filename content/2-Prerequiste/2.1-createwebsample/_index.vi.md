---
title : "Tạo trang web tĩnh S3"
date: 2024-06-18
 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---


### Khởi tạo S3 Bucket
- Truy cập **AWS Management Console**
- Đăng nhập bằng tài khoản của bạn.
- Sau khi đăng nhập xong sẽ chuyển người dùng đến trang chính của AWS Manage Console như hình :
  
  ![ConnectPrivate](/images/2.prerequisite/pic01.png) 


- Tìm và mở dịch vụ **S3**.
  
  ![ConnectPrivate](/images/2.prerequisite/pic02.png)
  ![ConnectPrivate](/images/2.prerequisite/pic03.png)

- Nhấn **Create bucket** ở trang chủ và điền các thông tin sau:
  ![ConnectPrivate](/images/2.prerequisite/pic04.png)
  
  |                                                               |
  |------------------------|--------------------------------------|
  | **AWS Region**         | Chọn cùng region với WAF (ví dụ: `us-east-1`) |
  | **Bucket name**        | `waf-demo-yourname`                  |

  ![ConnectPrivate](/images/2.prerequisite/pic05.png)

- Trong mục **Object Ownership**, ta chọn **ACLs disabled (recommended)**.

  ![ConnectPrivate](/images/2.prerequisite/pic06.png)

- Kế tiếp ở phần **Block Public Access settings**:
  - Bỏ chọn **Block all public access**.
  - Tích vào **I acknowledge that the current settings might result in this bucket and the objects within becoming public**.

  ![ConnectPrivate](/images/2.prerequisite/pic07.png)

- Giữ nguyên cài đặt khác mặc định, sau đó nhấn **Create bucket**.

---

### Upload file `index.html`
- Tạo file `index.html` với nội dung cơ bản:
```html
<!DOCTYPE html>
<html>
<head><title>WAF Demo</title></head>
<body><h1>Hello WAF!</h1></body>
</html>
````
- Truy cập bucket vừa tạo → Nhấn Upload.
  ![ConnectPrivate](/images/2.prerequisite/pic08.png)

  ![ConnectPrivate](/images/2.prerequisite/pic09.png)

- Chọn file index.html và nhấn Upload.
  ![ConnectPrivate](/images/2.prerequisite/pic10.png)

---

### Bật Static Website Hosting
- Trong bucket, mở tab **Properties**
- Cuộn xuống Static website hosting → Nhấn **Edit**.
- Chọn **Enable**.
- Ở phần Hosting type, chọn Host a static website.
- Mục Index document: nhập `index.html`.
- Nhấn Save changes.
- Sao chép Endpoint URL được hiển thị.

  ![ConnectPrivate](/images/2.prerequisite/pic11.png)

---

### Cấp quyền Public Access
- Vào tab Permissions của bucket.
- Cuộn xuống ngay tại phần **Bucket policy**, nhấn Edit và dán đoạn policy sau, đổi <your-bucket-name> bằng tên bucket của bạn:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<your-bucket-name>/*"
    }
  ]
}
````

- Nhấn Save changes.
  ![ConnectPrivate](/images/2.prerequisite/pic12.png)

- Kiểm tra truy cập: Truy cập lại trình duyệt thông qua **Endpoint URL** mà bạn đã tạo trước đó, nếu thấy nội dung "Hello WAF!" nghĩa là bạn đã thành công.