---
title: "Thiết lập PM2 để chạy nền"
date: 2025-07-10
weight: 3
chapter: false
pre: "<b>2.2.3</b>"
---

## Cài đặt PM2

PM2 là một process manager giúp ứng dụng Node.js luôn chạy nền và tự khởi động lại khi gặp lỗi hoặc sau khi reboot máy.

### 1. Cài đặt PM2:

```bash
npm install -g pm2
```

## Chạy ứng dụng với PM2

### 1. Điều hướng vào thư mục chứa project:

```bash
cd ~/todo-app
```

### 2. Chạy ứng dụng bằng PM2:

```bash
pm2 start app.js --name todo-app
```

### 3. Kiểm tra trạng thái:

```bash
pm2 status
```

## Thiết lập khởi động cùng hệ thống

### 1. Kích hoạt PM2 khởi động cùng hệ thống:

```bash
pm2 startup
```

### 2. Thực thi dòng lệnh được in ra (ví dụ):

```bash
sudo env PATH=$PATH:/home/ubuntu/.nvm/versions/node/v18.17.0/bin \\
pm2 startup systemd -u ubuntu --hp /home/ubuntu
```

### 3. Lưu trạng thái:

```bash
pm2 save
```

## Kiểm tra lại ứng dụng

### 1. Truy cập lại trình duyệt:

```
http://<EC2_PUBLIC_IP>:3000
```

### 2. Nếu máy chủ khởi động lại, ứng dụng vẫn sẽ chạy nhờ PM2.

## Các lệnh PM2 hữu ích

```bash
# Xem logs
pm2 logs todo-app

# Restart ứng dụng
pm2 restart todo-app

# Stop ứng dụng
pm2 stop todo-app

# Xóa ứng dụng khỏi PM2
pm2 delete todo-app

# Xem thông tin chi tiết
pm2 show todo-app
```

{{% notice tip %}}
PM2 cũng hỗ trợ log, restart tự động, cluster mode và quản lý nhiều ứng dụng — rất hữu ích cho môi trường production.
{{% /notice %}}
```
