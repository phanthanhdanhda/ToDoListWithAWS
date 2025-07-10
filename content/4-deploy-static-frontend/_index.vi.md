---
title: "Triển khai frontend tĩnh với S3 và CloudFront"
date: 2025-05-25
weight: 4
chapter: true
pre: "<b> 4. </b>"
---

{{% notice info %}}
Trong chương này, bạn sẽ triển khai giao diện web tĩnh (HTML/CSS/JS) của ứng dụng To-do List lên dịch vụ Amazon S3, sau đó sử dụng CloudFront để phân phối nội dung qua CDN.
{{% /notice %}}

---

### ✅ Mục tiêu

- Tạo bucket S3 để lưu trữ static site
- Cấu hình bucket cho phép public truy cập
- Triển khai frontend qua AWS CLI hoặc giao diện
- Tạo CloudFront Distribution để phân phối web toàn cầu

---

### 📚 Nội dung

- [Tạo S3 Bucket cho frontend](4.1-setup-s3/)
- [Triển khai static site lên S3](4.2-deploy-static-site/)
- [Cấu hình CloudFront phân phối nội dung](4.3-setup-cloudfront/)
