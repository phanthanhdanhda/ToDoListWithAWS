---
title: "Tạo VPC"
date: 2025-07-10
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

{{% notice info %}}
Trong bước này, bạn sẽ tạo một Virtual Private Cloud (VPC) tên là `TodoVPC` để chứa toàn bộ hạ tầng mạng của ứng dụng.
{{% /notice %}}

---

## 🧭 Các bước thực hiện

### 1. Truy cập VPC Console

- Truy cập: [VPC Console](https://console.aws.amazon.com/vpc/home)
- Chọn **Your VPCs**
- Click **Create VPC**

![VPC](/images/2.prerequisite/001-createvpc.png)

---

### 2. Cấu hình thông tin VPC

Tại màn hình **Create VPC**:

| Trường                | Giá trị                  |
|------------------------|--------------------------|
| **Name tag**          | `TodoVPC`               |
| **IPv4 CIDR block**   | `10.10.0.0/16`          |
| **Tenancy**           | default                 |

Giữ nguyên các tùy chọn còn lại → Click **Create VPC**

![VPC](/images/2.prerequisite/002-createvpc.png)

---

### 3. Kiểm tra trạng thái

Sau khi tạo xong, kiểm tra danh sách VPCs để đảm bảo VPC `TodoVPC` có trạng thái **available**.

---

## ✅ Kết quả mong đợi

- Tạo thành công VPC `TodoVPC` với dải IP riêng
- Sẵn sàng tạo subnet và các thành phần mạng khác bên trong VPC
