---
title : "Cấu hình ML-style detection"
date: 2024-06-18
 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

Trong bước này, chúng ta sẽ thực hiện các công đoạn gồm:
- Thu thập và phân tích log từ đó trích xuất đặc trưng (features) từ các request.
- Huấn luyện hoặc áp dụng mô hình ML để nhận diện pattern tấn công.
- Tạo luật WAF động (dynamic rules) dựa trên kết quả ML.

### Nội dung
3.1. [Tạo Lambda Function kiểm tra log WAF](3.1-createlambda/) \
3.2. [Subscribe Lambda với Log Group](3.2-3.2-subscribeLambda/)