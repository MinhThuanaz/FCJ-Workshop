---
title : "Bật logging và tạo Log Group"
date: 2024-06-18

weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

### Mục tiêu:
Ghi lại log request vào CloudWatch Logs để sau này dùng ML model phân tích.

- Vào lại AWS WAF console → WebACLs
- Chọn WebACL mà bạn vừa tạo.
  
  ![ConnectPrivate](/images/2.prerequisite/pic18.png)

- Sau khi hiện lên thông tin WebACL mà bạn đã tạo chọn mục **Logging and Metrics**
- Chọn **Enable** ở góc phải
- Chọn **Logging destination**
  
  ![ConnectPrivate](/images/2.prerequisite/pic19.png)

- Chọn **CloudWatch Logs** (phổ biến nhất)
  ![ConnectPrivate](/images/2.prerequisite/pic20.png)

- Nếu chưa có Log Group:
    + Mở tab mới vào CloudWatch → Log groups → Create log group.
    + Đặt tên (ví dụ: /aws/waf/ml-waf-logs).
  ![ConnectPrivate](/images/2.prerequisite/pic21.png)

    + Quay lại màn hình WAF, chọn Log Group vừa tạo.
    + Nhấp **save** và bạn đã thành công bật logging
  ![ConnectPrivate](/images/2.prerequisite/pic22.png)
