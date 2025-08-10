---
title : "Tạo WAF WebACL và gán vào resource"
date: 2024-06-18

weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Tạo một WebACL

- Quay lại trang chủ AWS console và mở **AWS WAF** console
  ![ConnectPrivate](/images/2.prerequisite/pic14.png)
- Tiếp đó chọn **WebACLs** và nhấp chọn **Create WebACL**
  ![ConnectPrivate](/images/2.prerequisite/pic13.png)

- Tên WebACL: Ví dụ ML-WAF-Demo.
- **Add AWS Resources** → chọn resource muốn bảo vệ (chọn CloudFront distribution mà chúng ta đã tạo trước đó).
- Rules: Tạm để trống (sẽ thêm ở bước tiếp theo).
- Default action: Allow.
- Hoàn tất tạo WebACL.
  ![ConnectPrivate](/images/2.prerequisite/pic15.png)

  ![ConnectPrivate](/images/2.prerequisite/pic16.png)

  ![ConnectPrivate](/images/2.prerequisite/pic17.png)