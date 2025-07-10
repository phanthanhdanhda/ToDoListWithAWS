---
title: "Cài đặt môi trường ứng dụng"
date: 2025-05-25
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

{{% notice info %}}
Trong phần này, bạn sẽ SSH vào EC2 instance để cài đặt môi trường Node.js và MongoDB (cài đặt local), chuẩn bị để chạy ứng dụng web **To-do List**.
{{% /notice %}}

---

## 🧰 Nội dung

Bạn sẽ thực hiện 3 bước quan trọng để chuẩn bị môi trường ứng dụng:

- ✅ **Cài đặt Node.js và MongoDB**
- ✅ **Cấu hình ứng dụng To-do List và kiểm thử**
- ✅ **Thiết lập PM2 để ứng dụng luôn chạy nền và khởi động cùng hệ thống**

---

## 📚 Mục lục

- [2.2.1 – Cài đặt Node.js và MongoDB](2.2.1-install-node/)
- [2.2.2 – Cấu hình ứng dụng và chạy thử](2.2.2-config-run-app/)
- [2.2.3 – Thiết lập PM2 để chạy nền](2.2.3-setup-pm2/)

---

{{% notice tip %}}
💡 Đây là bước quan trọng để đảm bảo ứng dụng hoạt động ổn định trước khi tiến hành deploy thực sự với CI/CD và các dịch vụ khác của AWS.
{{% /notice %}}
