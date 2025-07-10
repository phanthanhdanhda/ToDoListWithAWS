---
title: "Xoá VPC và các thành phần liên quan"
date: 2025-05-25
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

Sau khi xóa toàn bộ EC2, bạn có thể xóa VPC tùy chỉnh và các thành phần liên quan:

---

### 🧹 1. Xoá Subnet

1. Truy cập [VPC Console](https://console.aws.amazon.com/vpc)
2. Chọn **Subnets** → Xóa cả `TodoPublicSubnet` nếu không còn dùng

---

### 🧹 2. Xoá Internet Gateway

1. Chọn **Internet Gateways**
2. **Detach** khỏi VPC nếu đang gắn → rồi **Delete**

---

### 🧹 3. Xoá Route Table

1. Chọn **Route Tables**
2. Chọn custom route table → **Delete**

---

### 🧹 4. Xoá VPC

1. Vào **Your VPCs**
2. Chọn `TodoVPC` → bấm **Delete**

---

> ✅ Sau khi hoàn tất, bạn đã giải phóng toàn bộ tài nguyên AWS đã sử dụng trong workshop này.
