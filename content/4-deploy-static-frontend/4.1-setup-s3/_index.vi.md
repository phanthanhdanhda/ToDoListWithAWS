---
title: "Tạo S3 Bucket cho frontend"
date: 2025-07-10
weight: 1
chapter: false
pre: "<b> 4.1 </b>"
---

## Tạo S3 bucket để lưu trữ frontend

Trong bước này, bạn sẽ tạo một S3 bucket để lưu trữ source code giao diện tĩnh của ứng dụng To-do List.

---

### 🔧 Bước 1: Truy cập giao diện quản lý S3

1. Vào [Amazon S3 Console](https://s3.console.aws.amazon.com/s3/home)
2. Click **Create bucket**

![S3](/images/4-deploy-static-frontend/001-create-bucket.png)

---

### 📥 Bước 2: Nhập thông tin bucket

- **Bucket name**: tên duy nhất, ví dụ: `todo-frontend-<your-name>`
- Bỏ chọn **Block all public access** để cho phép truy cập public
- Check xác nhận cảnh báo bảo mật

![S3](/images/4-deploy-static-frontend/002-create-bucket.png)

---

### 🛡️ Bước 3: Tắt chặn truy cập public

1. Sau khi tạo, vào tab **Permissions**
2. Tìm mục **Block public access (bucket settings)**
3. Click **Edit**, bỏ chọn tất cả, rồi **Save**

---

### 🌍 Bước 4: Cho phép public đọc nội dung

1. Vào tab **Permissions** → **Bucket Policy** → **Edit**

![S3](/images/4-deploy-static-frontend/003-bucket-policy.png)

2. Dán đoạn policy sau vào:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::todo-frontend-<your-name>/*"
    }
  ]
}
```

3. Nhấn chọn **Save Changes**

![S3](/images/4-deploy-static-frontend/004-bucket-policy.png)

```

{{% notice tip %}}
📌 Thay <your-name> bằng đúng tên bucket bạn đã đặt.
{{% /notice %}}

{{% notice success %}}
✅ Bạn đã tạo thành công một bucket S3 có thể public để chứa frontend.
{{% /notice %}}

Tiếp theo, chúng ta sẽ upload mã nguồn HTML/CSS/JS lên bucket này.