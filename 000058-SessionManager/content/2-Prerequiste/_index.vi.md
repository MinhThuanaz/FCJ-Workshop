---
title : "Các bước chuẩn bị"
date: 2024-06-18

weight : 2 
chapter : false
pre : " <b> 2. </b> "
---


Trong phần này, bạn sẽ tạo môi trường demo để sẵn sàng triển khai WAF thông minh, gồm:
- **Ứng dụng web mẫu** để WAF bảo vệ (S3 hoặc EC2).
- **AWS WAF WebACL** để chặn các truy cập nguy hiểm.
- **CloudWatch Log Group** để ghi lại các sự kiện bảo mật từ WAF
  
Để tìm hiểu cách tạo các EC2, S3,... các bạn có thể tham khảo bài lab :
  - [Giới thiệu về Amazon EC2](https://000004.awsstudygroup.com/vi/)
  - [Làm việc với Amazon S3](https://000057.awsstudygroup.com/vi/)
  - [Làm việc với Amazon WAF](https://000026.awsstudygroup.com/vi/)
  - [Giới thiệu về Amazon Lambda](https://000022.awsstudygroup.com/vi/)


### Nội dung
  - [Chuẩn bị VPC và EC2 Instance](2.1-createwebsample/)
  - [Tạo WAF WebACL và gán vào resource](2.2-createWAFwebacl/)
  - [Bật logging và tạo Log Group](2.3-turnonloggingcreateLogGroup/)