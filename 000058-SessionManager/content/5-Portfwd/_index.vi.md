---
title : "Kiểm tra và xác nhận"
date: 2024-06-18 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

### Mục tiêu
- Kiểm tra xem **Rate Limiting Rule** và **Geo-blocking Rule** đã hoạt động đúng như thiết kế.
- Đảm bảo không gây ảnh hưởng tới người dùng.

---

### Trường hợp kiểm thử Rate Limiting Rule
1. Sử dụng công cụ `ab` (Apache Benchmark) hoặc `hey` để gửi **3000 request** trong vòng **5 phút** đến endpoint `/api/login`.
2. Kỳ vọng:
   - Request vượt quá 2000/5 phút từ cùng một IP sẽ bị **match rule** và ghi log.
   - Vì đang ở chế độ `COUNT`, request vẫn được trả về nhưng sẽ thấy log match trong CloudWatch.



### Trường hợp kiểm thử Geo-blocking Rule
1. Sử dụng VPN để chọn IP từ quốc gia trong danh sách block (ví dụ: `RU`).
2. Gửi request đến trang chủ hoặc endpoint `/api/data`.
3. Kỳ vọng:
   - Request từ IP thuộc quốc gia đó sẽ bị match Geo-blocking Rule và ghi log.
   - Ở chế độ `COUNT`, vẫn nhận được phản hồi nhưng có entry log.

---

### Cách xác minh
- Vào **AWS WAF → WebACL → Sampled requests** để xem request match rule nào.
- Kiểm tra **CloudWatch Metrics**:
  - `RateLimitAPI` → tăng sau khi chạy load test.
  - `GeoBlockHighRisk` → tăng khi request từ IP quốc gia bị block.
- Đảm bảo không có match từ người dùng hợp lệ ngoài dự kiến.
