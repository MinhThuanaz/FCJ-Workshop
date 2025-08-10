---
title : "Tạo CloudFront Distributions cho web tĩnh S3"
date: 2024-06-18

weight : 1
chapter : false
pre : " <b> 2.1.1 </b> "
---

## Tạo CloudFront Distribution

### Mở dịch vụ CloudFront
- Trong AWS Management Console, tìm **CloudFront** → **Create distribution**.

### Specify Origin
- **Origin type**: Chọn **Amazon S3**.
- **Origin domain**: Chọn bucket S3 đã tạo.
- Nếu bucket đã bật Static website hosting → nhấn **Use website endpoint** để CloudFront phục vụ đúng file index.html.
- **Allow private S3 bucket access to CloudFront**: bật nếu muốn giới hạn truy cập chỉ qua CloudFront.

### Cấu hình Cache & Security
- **Viewer protocol policy**: Redirect HTTP to HTTPS.
- **Default root object**: `index.html`.

### Bỏ qua bước Enable security nếu bạn muốn tiết kiệm phí
- Ở bước **Enable security (WAF)**:
  - Chọn **Do not enable security protections** để chưa gắn WAF.
  - Sau này vào AWS WAF console để gắn WebACL khi cần test.

### Tạo Distribution
- Nhấn **Create distribution**.
- Chờ trạng thái **Deployed**.
