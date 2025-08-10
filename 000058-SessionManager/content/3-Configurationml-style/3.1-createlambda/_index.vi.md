---
title : "Tạo Lambda Function kiểm tra log WAF"
date: 2024-06-18

weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

### Mục tiêu:
- Lambda sẽ nhận log từ WAF (CloudWatch Logs hoặc Kinesis), phân tích và phát hiện dấu hiệu tấn công dựa trên logic ML hoặc rule tùy chỉnh.

### Bắt đầu thực hiện
- Vào Lambda Console: truy cập [AWS Lambda Console](https://console.aws.amazon.com/lambda/home?region=us-east-1)
- Nhấp chọn **Create a function**
  ![ConnectPrivate](/images/3.connect/pic01.png)

- Sau khi hiển thị lên chọn cách tạo gồm:
  - Author from scratch
  - Function name: `waf-ml-detection`
  - Runtime: Python 3.10 (hoặc Node.js)
  - Architecture: x86_64
  - Permissions:
    - Chọn **Create a new role with basic Lambda permissions**.
  - Chọn **Create function**
  ![ConnectPrivate](/images/3.connect/pic02.png)
  ![ConnectPrivate](/images/3.connect/pic03.png)

### Thêm quyền đọc log
- Sau khi tạo xong Lambda → vào tab Configuration → Permissions.
  ![ConnectPrivate](/images/3.connect/pic04.png)
- Chọn Role name để mở IAM Role.
  ![ConnectPrivate](/images/3.connect/pic05.png)
  ![ConnectPrivate](/images/3.connect/pic06.png)
- Trong Role cuộn xuống tìm **Add permissions** sau đó chọn **Attach policies** và gắn:
  - CloudWatchLogsReadOnlyAccess (đọc log)
  - AWSWAFReadOnlyAccess (nếu cần đọc cấu hình WAF)
  ![ConnectPrivate](/images/3.connect/pic07.png)

### Viết code Lambda
- Quay lại tab Code bên lambda, thay nội dung bằng mẫu Python cơ bản:
```python
import json
def lambda_handler(event, context):
    for record in event['records']:
        payload = json.loads(record['data'])
        # Log payload để debug
        print(json.dumps(payload))
        
        # Ví dụ rule: phát hiện nếu request chứa SQL injection pattern
        if "UNION" in payload.get("httpRequest", {}).get("uri", "").upper():
            print("🚨 Detected possible SQL injection attack!")
            # Ở đây có thể gửi alert hoặc gọi API WAF để block IP
        
    return {"statusCode": 200, "body": "Processed"}
```
- Deploy code
  ![ConnectPrivate](/images/3.connect/pic08.png)
  ![ConnectPrivate](/images/3.connect/pic09.png)