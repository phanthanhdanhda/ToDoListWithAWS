---
title: "Cấu hình CloudFront phân phối nội dung"
date: 2025-05-25
weight: 3
chapter: false
pre: "<b> 4.3 </b>"
---

## Cấu hình CloudFront phân phối nội dung

Trong bước này, bạn sẽ cấu hình **CloudFront** để phân phối nội dung giao diện tĩnh từ S3 với tốc độ nhanh hơn và domain dễ nhớ hơn.

---

### 🌐 Bước 1: Truy cập CloudFront

1. Mở [AWS CloudFront Console](https://console.aws.amazon.com/cloudfront/)
2. Click **Create Distribution**

![CF](/images/4-deploy-static-frontend/011-create-distribution.png)

---

### 📥 Bước 2: Cấu hình Origin

Tại phần **Origin Settings**:

- **Origin domain**: Chọn bucket S3 bạn đã bật Static website hosting  
  ⛔ Không chọn loại S3 endpoint mặc định (`s3.amazonaws.com`), hãy chọn loại có dạng `s3-website...`
- **Origin access**: Chọn **Public** (nếu bạn chưa dùng OAC)
- **Viewer protocol policy**: Chọn **Redirect HTTP to HTTPS**

![CF](/images/4-deploy-static-frontend/012-create-distribution.png)

---

### 🛠️ Bước 3: Cấu hình default behavior

- **Cache policy**: `CachingOptimized`
- **Response headers policy**: `SecurityHeadersPolicy` (nếu có)
- **Compress objects automatically**: ✅ Enabled
- Click **Create distribution**

![CF](/images/4-deploy-static-frontend/013-create-distribution.png)

---

### 🕒 Bước 4: Chờ CloudFront hoạt động

- Bạn sẽ thấy một dòng trạng thái “In Progress”
- Chờ khoảng 5–10 phút đến khi chuyển sang **Enabled**

![CF](/images/4-deploy-static-frontend/014-create-distribution.png)

---

### 🔗 Bước 5: Truy cập qua CloudFront

- Tại cột **Domain name**, bạn sẽ thấy tên miền có dạng:

  `d123456abcdef8.cloudfront.net`

![CF](/images/4-deploy-static-frontend/015-create-distribution.png)

- Truy cập domain đó để xem frontend hoạt động

![CF](/images/4-deploy-static-frontend/016-create-distribution.png)

---

### ✅ Hoàn tất

Giao diện To-do List đã được phân phối toàn cầu thông qua CloudFront!

Bạn có thể sử dụng domain CloudFront này để kết nối frontend với API (backend chạy trên EC2).
