---
title: "Cài đặt Node.js và MongoDB"
date: 2025-07-10
weight: 1
chapter: false
pre: "<b>2.2.1</b>"
---

## SSH vào EC2

1. Mở terminal (PowerShell hoặc bash).
2. SSH vào instance bằng private key:

```bash
ssh -i ~/path/to/LabKeypair.pem ubuntu@<EC2_PUBLIC_IP>
```

## Cài đặt Node.js

### Cài đặt Node.js phiên bản LTS:

```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Kiểm tra phiên bản:

```bash
node -v
npm -v
```

## Cài đặt MongoDB (local)

### 1. Import GPG key:

```bash
curl -fsSL https://pgp.mongodb.com/server-6.0.asc | \\
  sudo gpg -o /usr/share/keyrings/mongodb-server-6.0.gpg \\
  --dearmor
```

### 2. Thêm repository:

```bash
echo "deb [ signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg ] \\
https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/6.0 multiverse" | \\
sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
```

### 3. Cài MongoDB:

```bash
sudo apt update
sudo apt install -y mongodb-org
```

### 4. Khởi động dịch vụ MongoDB:

```bash
sudo systemctl start mongod
sudo systemctl enable mongod
```

### 5. Kiểm tra trạng thái MongoDB:

```bash
sudo systemctl status mongod
```

{{% notice tip %}}
Bạn đã sẵn sàng để triển khai ứng dụng sau khi hoàn tất bước này.
{{% /notice %}}
```
