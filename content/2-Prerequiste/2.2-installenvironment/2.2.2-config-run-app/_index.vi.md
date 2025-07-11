---
title: "Cấu hình ứng dụng và chạy thử"
date: 2025-07-10
weight: 2
chapter: false
pre: "<b>2.2.2</b>"
---

## Clone mã nguồn

### 1. Tạo thư mục dự án:

```bash
mkdir -p ~/todo-app && cd ~/todo-app
```

### 2. Clone mã nguồn từ GitHub:

```bash
git clone https://github.com/your-username/todo-list-app.git .
```

### 3. Cài đặt các gói phụ thuộc:

```bash
npm install
```

## Cấu hình .env (nếu cần)

### 1. Tạo file .env nếu chưa có:

```bash
touch .env
```

### 2. Thêm cấu hình MongoDB local:

```env
MONGO_URI=mongodb://localhost:27017/todoapp
PORT=3000
```

## Chạy ứng dụng thử

### 1. Chạy ứng dụng:

```bash
node app.js
```

### 2. Truy cập trình duyệt và nhập:

```
http://<EC2_PUBLIC_IP>:3000
```

### 3. Kiểm tra xem giao diện web To-do List đã hiển thị chưa.

{{% notice tip %}}
Nếu bạn không truy cập được, hãy kiểm tra lại:
- Cổng 3000 đã mở trong Security Group
- Dịch vụ đã được start thành công
- Địa chỉ IP là đúng public IP của EC2 instance
{{% /notice %}}
```
