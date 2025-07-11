---
title: "Triển khai backend và CI/CD"
date: 2025-07-10
weight: 3
chapter: true
pre: "<b> 3. </b>"
---

{{% notice info %}}
Chương này hướng dẫn bạn triển khai ứng dụng Node.js (To-do List) trên EC2 và thiết lập CI/CD bằng GitHub Actions để tự động triển khai mỗi khi có thay đổi.
{{% /notice %}}

---

### Mục tiêu:

- Triển khai ứng dụng thực tế bằng script tự động khi EC2 khởi động
- Thiết lập reverse proxy với Nginx để phục vụ ứng dụng qua cổng 80
- Thiết lập tường lửa hợp lý
- Tự động hoá deploy backend bằng GitHub Actions

---

### Nội dung

- [Triển khai ứng dụng Node.js lên EC2](3.1-deploy-on-ec2/)
- [Thiết lập CI/CD với GitHub Actions](3.2-setup-cicd-githubactions/)
