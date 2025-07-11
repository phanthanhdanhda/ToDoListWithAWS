---
title: "Triển khai ứng dụng trên EC2"
date: 2025-07-10
weight: 1
chapter: false
pre: "<b>3.1</b>"
---

{{% notice info %}}
Trong phần này, bạn sẽ thiết lập ứng dụng Node.js để chạy nền bằng PM2, giúp ứng dụng luôn hoạt động ổn định kể cả khi EC2 instance bị khởi động lại.
{{% /notice %}}

---

## 1. SSH vào EC2

Từ máy tính của bạn, mở terminal và chạy lệnh sau (đảm bảo đang ở thư mục chứa file `.pem`):

```bash
ssh -i LabKeypair.pem ubuntu@<EC2_PUBLIC_IP>
```

## 2. Cài đặt PM2

PM2 là process manager giúp quản lý ứng dụng Node.js chạy nền:

```bash
npm install -g pm2
```

### Kiểm tra cài đặt:

```bash
pm2 --version
```

## 3. Khởi chạy ứng dụng với PM2

### 1. Di chuyển vào thư mục ứng dụng:

```bash
cd ~/todo-app
```

### 2. Khởi động ứng dụng với PM2:

```bash
pm2 start app.js --name todo-app
```

### 3. Kiểm tra trạng thái:

```bash
pm2 list
```

Bạn sẽ thấy output tương tự:

```
┌─────┬──────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
│ id  │ name     │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
├─────┼──────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
│ 0   │ todo-app │ default     │ 1.0.0   │ fork    │ 12345    │ 2s     │ 0    │ online    │ 0%       │ 25.2mb   │ ubuntu   │ disabled │
└─────┴──────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
```

## 4. Thiết lập tự khởi động sau reboot

### 1. Tạo startup script:

```bash
pm2 startup
```

### 2. Lệnh trên sẽ in ra một dòng như sau (ví dụ):

```bash
sudo env PATH=$PATH:/home/ubuntu/.nvm/versions/node/v20.5.0/bin \\
pm2 startup systemd -u ubuntu --hp /home/ubuntu
```

### 3. Hãy copy dòng đó và chạy lại trong terminal.

### 4. Lưu trạng thái hiện tại:

```bash
pm2 save
```

## 5. Kiểm tra sau reboot (tùy chọn)

### 1. Thử reboot EC2:

```bash
sudo reboot
```

### 2. Sau khi EC2 khởi động lại, SSH lại vào:

```bash
ssh -i LabKeypair.pem ubuntu@<EC2_PUBLIC_IP>
```

### 3. Kiểm tra PM2:

```bash
pm2 list
```

Ứng dụng `todo-app` vẫn sẽ đang chạy.

### 4. Test ứng dụng:

```bash
curl http://localhost:3000
```

## 6. Các lệnh PM2 hữu ích

### Quản lý processes:

```bash
# Xem logs realtime
pm2 logs todo-app

# Restart ứng dụng
pm2 restart todo-app

# Stop ứng dụng
pm2 stop todo-app

# Xem thông tin chi tiết
pm2 show todo-app

# Monitoring dashboard
pm2 monit
```

### Troubleshooting:

```bash
# Nếu ứng dụng không start
pm2 logs todo-app --lines 50

# Kiểm tra file có tồn tại không
ls -la ~/todo-app/app.js

# Kiểm tra port có bị chiếm không
sudo netstat -tlnp | grep :3000
```

## 7. Kiểm tra ứng dụng từ browser

### 1. Đảm bảo Security Group đã mở port 3000:
- Vào AWS Console → EC2 → Security Groups
- Thêm Inbound Rule: Type: Custom TCP, Port: 3000, Source: 0.0.0.0/0

### 2. Truy cập ứng dụng:

```
http://<EC2_PUBLIC_IP>:3000
```

## Kết quả mong đợi

- ✅ Ứng dụng chạy ổn định với PM2
- ✅ Tự động khởi động lại sau reboot
- ✅ Có thể truy cập từ browser
- ✅ Logs được quản lý bởi PM2

{{% notice success %}}
💡 **Chúc mừng!** Bạn đã hoàn tất việc triển khai ứng dụng Node.js dạng chạy nền trên EC2 bằng PM2.
{{% /notice %}}

{{% notice tip %}}
Để tối ưu hóa production, hãy xem xét sử dụng reverse proxy như Nginx và SSL certificate cho HTTPS.
{{% /notice %}}
```
