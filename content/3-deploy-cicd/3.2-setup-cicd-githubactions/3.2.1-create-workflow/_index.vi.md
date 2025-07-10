---
title: "Tạo file workflow CI/CD"
date: 2025-05-25
weight: 1
chapter: false
pre: "<b>3.2.1</b>"
---

## Tạo workflow GitHub Actions

Chúng ta sẽ tạo một workflow đơn giản để:
- **SSH** vào **EC2**.
- **Pull code** mới từ **GitHub**.
- Cài đặt **dependency** và khởi động lại ứng dụng với **PM2**.

---

### 🛠️ Bước 1: Tạo thư mục `.github/workflows`

Tại thư mục gốc của dự án Node.js, tạo cấu trúc sau:

```bash
mkdir -p .github/workflows
```

---

### 📝 Bước 2: Tạo file `deploy.yml`

Tạo file `.github/workflows/deploy.yml` với nội dung như sau:

```yaml
name: Deploy To EC2

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Deploy to EC2 via SSH
      uses: appleboy/ssh-action@v0.1.10
      with:
        host: ${{ secrets.EC2_HOST }}
        username: ${{ secrets.EC2_USER }}
        key: ${{ secrets.EC2_KEY }}
        script: |
          cd todo-app
          git pull origin main
          npm install
          pm2 restart all || pm2 start index.js --name todo
```

---

### 🔐 Bước 3: Tạo GitHub Secrets

Trên trang GitHub repo của bạn:

1. Vào **Settings → Secrets and variables → Actions**.

![Sec](/images/3.deploy/001-github-secret.png)

2. Nhấn **New repository secret**.

![Sec](/images/3.deploy/002-github-secret.png)

3. Tạo các biến sau:

| Tên biến   | Ý nghĩa                            |
| ---------- | ---------------------------------- |
| `EC2_HOST` | Public IP của EC2                  |
| `EC2_USER` | Tên user để SSH, ví dụ `ubuntu`    |
| `EC2_KEY`  | Nội dung file `.pem` (private key) |

![Sec](/images/3.deploy/003-github-secret.png)

---

{{% notice success %}}
✅ Sau khi hoàn thành, mỗi khi bạn push code lên nhánh main, workflow sẽ tự động kết nối vào EC2, pull code mới và restart lại ứng dụng với PM2.
{{% /notice %}}