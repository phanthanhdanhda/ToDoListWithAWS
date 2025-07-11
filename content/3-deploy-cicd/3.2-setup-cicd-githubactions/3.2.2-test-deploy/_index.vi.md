---
title: "Push code và kiểm tra deploy"
date: 2025-07-10
weight: 2
chapter: false
pre: " <b> 3.2.2 </b> "
---

## Push code và kiểm tra workflow

Sau khi đã tạo file workflow CI/CD, bạn có thể kiểm tra bằng cách push lên GitHub.

---

### 🚀 Bước 1: Push code lên GitHub

```bash
git add .
git commit -m "Thiết lập CI/CD deploy với GitHub Actions"
git push origin main
```

---

### 📦 Bước 2: Kiểm tra workflow trên GitHub

1. Truy cập repo GitHub của bạn
2. Vào tab **Actions**

![Act](/images/3.deploy/004-github-action.png)

3. Chọn workflow **Deploy To EC2**

![Sec](/images/3.deploy/005-github-action.png)

4. Kiểm tra quá trình thực thi các bước:
   - Kết nối EC2
   - Pull code
   - Cài npm install
   - Khởi động lại ứng dụng với PM2

---

### 🌐 Bước 3: Truy cập ứng dụng

Mở trình duyệt và truy cập vào:

```
http://<EC2_PUBLIC_IP>:3000
```

Nếu mọi thứ chính xác, bạn sẽ thấy giao diện web To-do List hoạt động đúng sau mỗi lần push code.

{{% notice tip %}}
Bạn nên kiểm tra pm2 logs trên EC2 nếu ứng dụng không phản hồi sau deploy.
{{% /notice %}}