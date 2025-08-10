---
title : "Subscribe Lambda với Log Group"
date: 2024-06-18

weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---


- Thông qua đường link truy cập này để quay về trang CloudWatch Console: [CloudWatch Console](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#logsV2:log-groups)
- Tìm Log Group mà bạn đã cấu hình ở bước trước cho WAF
  ![ConnectPrivate](/images/3.connect/pic10.png)

- Chọn Log Group → Actions → Create subscription filter.
  ![ConnectPrivate](/images/3.connect/pic11.png)

- Chọn các mục sau gồm có:
  - Destination: **Lambda function**
  - Lambda: `waf-ml-detection`
  - Đặt tên Subscription filter name: `waf-logs-to-lambda`
- Filter pattern: Để trống (nghĩa là gửi tất cả log).
- Xác nhận và tạo thành công.
  ![ConnectPrivate](/images/3.connect/pic12.png)