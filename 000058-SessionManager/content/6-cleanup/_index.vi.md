+++
title = "Dọn dẹp tài nguyên  "
date = 2021
weight = 6
chapter = false
pre = "<b>6. </b>"
+++



#### Xóa S3 bucket

- Truy cập [giao diện quản trị dịch vụ S3](https://s3.console.aws.amazon.com/s3/home)
  + Click chọn S3 bucket chúng ta đã tạo 
  + Click **Empty**.
  + Điền **permanently delete**, sau đó click **Empty** để tiến hành xóa object trong bucket.
  + Click **Exit**.

- Sau khi xóa hết object trong bucket, click **Delete**

- Điền tên S3 bucket, sau đó click **Delete bucket** để tiến hành xóa S3 bucket.


#### Xóa Web ACLs
- Truy cập [giao diện WAF & SHIELD](https://us-east-1.console.aws.amazon.com/wafv2/homev2/start?region=global)
   + Chọn **WebACLs** tiếp chọn webacls mà ta đã tạo
   + Click **Delete** điền delete để xác nhận xóa WebACl (phải hủy **Disassociate** với Cloudfront mới xóa được)
  

#### Xóa Log Group bên CloudWatch
- Chọn log groups đã tạo
- Nhấp chọn muc **Actions**
- Chọn **delete log group(s)**
- Xác nhận Delete


#### Xóa Lambda
- Truy cập [giao diện Lambda](https://us-east-1.console.aws.amazon.com/lambda/home?region=us-east-1#/discover)
   + Chọn mục **Functions** bên thanh menu bên trái
   + Nhấp chọn function đã tạo 
   + Chọn **Actions**
   + Nhấp **delete**
   + Điền **confirm** để xác nhận xóa


#### Xóa ClouFront Distribution
- Truy cập [giao diện CloudFront](https://us-east-1.console.aws.amazon.com/cloudfront/v4/home?region=us-east-1#/distributions)
   + Chọn **Distributions** bên thanh menu
   + Nhấp chọn distribution đã tạo
   + Chọn **Disable** (Cần phải tắt trước khi có thể xóa distribution)
   + Chọn **Delete**