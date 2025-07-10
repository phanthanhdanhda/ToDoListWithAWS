---
title: "Xoá EC2, S3, CloudFront, Security Group & Key Pair"
date: 2025-05-25
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

Trong bước này, bạn sẽ xóa các tài nguyên sau:

- EC2 Instance
- Security Group
- S3 Bucket
- CloudFront Distribution
- Key Pair (nếu không dùng nữa)

---

### 🧹 1. Xoá EC2 Instance

1. Truy cập [EC2 Console](https://console.aws.amazon.com/ec2/v2/home)
2. Chọn instance tên `To-do EC2`
3. Bấm **Instance State → Terminate instance**
4. Xác nhận

---

### 🧹 2. Xoá Security Group

1. Truy cập menu **Security Groups** (trong EC2 hoặc VPC)
2. Xoá security group tên `TodoSG`

> 💡 Nếu security group còn gắn với EC2 hoặc resource nào khác, bạn cần gỡ ra trước khi xóa.

---

### 🧹 3. Xoá Key Pair

1. Truy cập [EC2 → Key Pairs](https://console.aws.amazon.com/ec2/v2/home?#KeyPairs)
2. Nếu bạn đã tạo `LabKeypair` hoặc tương tự chỉ để thực hành, bạn có thể xóa.

---

### 🧹 4. Xoá S3 Bucket

1. Truy cập [S3 Console](https://s3.console.aws.amazon.com/s3)
2. Chọn bucket chứa static site (ví dụ: `todo-frontend-bucket`)
3. Bấm **Empty** trước → sau đó **Delete bucket**

---

### 🧹 5. Xoá CloudFront Distribution

1. Truy cập [CloudFront Console](https://console.aws.amazon.com/cloudfront)
2. Chọn distribution vừa tạo → **Disable**
3. Sau khi trạng thái là **Disabled**, bấm **Delete**

> ⚠️ CloudFront cần vài phút để chuyển sang trạng thái Disabled trước khi xoá được.
