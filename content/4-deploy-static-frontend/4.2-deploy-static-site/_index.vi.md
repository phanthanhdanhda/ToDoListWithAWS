---
title: "Triển khai static site lên S3"
date: 2025-07-10
weight: 2
chapter: false
pre: "<b> 4.2 </b>"
---

## Triển khai static site lên S3

Trong bước này, bạn sẽ upload giao diện tĩnh (HTML, CSS, JS) của ứng dụng To-do List lên S3 bucket để public trên web.

---

### 📁 Bước 1: Chuẩn bị mã nguồn giao diện

1. Mở thư mục project To-do List
2. Vào thư mục chứa frontend (ví dụ `public/` hoặc `frontend/`)
3. Đảm bảo có file `index.html` và các file tĩnh cần thiết khác (style.css, script.js, v.v.)

---

### ☁️ Bước 2: Upload giao diện lên S3

#### Cách 1: Dùng AWS CLI (khuyến khích)

```bash
aws s3 sync ./public s3://todo-frontend-<your-name> --acl public-read
```

{{% notice tip %}}
./public: thư mục chứa file giao diện

Thay <your-name> bằng tên bucket thực tế
{{% /notice %}}

#### Cách 2: Dùng giao diện AWS S3

1. Vào bucket bạn đã tạo
2. Click **Upload** → **Add files** hoặc **Add folder**

![S3](/images/4-deploy-static-frontend/005-upload-bucket.png)

3. Chọn toàn bộ nội dung frontend (index.html, assets, v.v.)
4. Click **Upload**

---

### 🌐 Bước 3: Bật Static Website Hosting

1. Trong bucket → tab **Properties**

![S3](/images/4-deploy-static-frontend/006-static-host.png)

2. Kéo xuống phần **Static website hosting**
3. Click **Edit**

![S3](/images/4-deploy-static-frontend/007-static-host.png)

4. Chọn **Enable**

![S3](/images/4-deploy-static-frontend/008-static-host.png)

5. Nhập:
   - **Index document**: index.html
   - (Nếu có) **Error document**: 404.html

![S3](/images/4-deploy-static-frontend/009-static-host.png)

6. Click **Save changes**

---

### 🧪 Bước 4: Truy cập trang web

Sau khi bật Static website hosting, bạn sẽ thấy **Bucket website endpoint**

![S3](/images/4-deploy-static-frontend/010-bucket-website.png)

Click vào link đó hoặc copy dán vào trình duyệt

{{% notice tip %}}
📌 Ví dụ: http://todo-frontend-yourname.s3-website-ap-southeast-1.amazonaws.com
{{% /notice %}}

{{% notice success %}}
✅ Giao diện frontend To-do List đã được triển khai thành công trên S3.
{{% /notice %}}

Tiếp theo, ta sẽ cấu hình CloudFront để tăng tốc và cấp phát domain đẹp.