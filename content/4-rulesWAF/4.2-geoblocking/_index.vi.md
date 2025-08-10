---
title : "Thiết lập Geo-Blocking Rules"
date: 2024-06-18

weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---


### Mục tiêu
- Hạn chế hoặc chặn truy cập từ những quốc gia/vùng lãnh thổ có nguy cơ cao hoặc không phục vụ thị trường.

### Thiết lập trên AWS Console
1. Trong WebACL, chọn **Add rules → Add my own rules and rule groups**.
2. Đặt tên rule: `GeoBlock-HighRisk`.
3. Chọn **Geo match**.
4. Thêm country codes cần block: ví dụ `["RU", "CN", "KP"]`.
5. Nếu cần whitelist IP hợp lệ từ quốc gia này, tạo IPSet whitelist và dùng NOT statement.
6. Action: **Count** để theo dõi.
7. Enable CloudWatch metrics và sampled requests.
8. Save và deploy.