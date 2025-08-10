---
title : "Thiết lập Rate Limiting Rule"
date: 2024-06-18

weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---


### Mục tiêu
- Giới hạn số lượng request từ cùng một IP trong khoảng thời gian nhất định nhằm giảm tải và ngăn chặn tấn công brute-force hoặc bot traffic.

### Thiết lập trên AWS Console
1. Vào **AWS WAF & Shield** trong AWS Management Console.
2. Chọn **WebACL** mà bạn muốn thêm rule.
3. Chọn **Add rules** → **Add my own rules and rule groups**.
4. Đặt tên rule: `RateLimit-API`.
5. Chọn **Rate-based rule**.
6. Cấu hình:
   - Limit: `2000` requests / 5 phút / IP.
   - Aggregate key: `IP`.
   - Scope-down: áp dụng cho URI path `/api/` hoặc `/login`.
7. Action: **Count** để theo dõi trước khi chặn.
8. Enable CloudWatch metrics và sampled requests.
9. Save và deploy.