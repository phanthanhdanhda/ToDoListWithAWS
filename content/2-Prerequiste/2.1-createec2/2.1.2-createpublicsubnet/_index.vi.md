---
title: "Tạo Subnet"
date: 2025-05-25
weight: 2
chapter: false
pre: " <b> 2.1.2 </b> "
---

{{% notice info %}}
Trong bước này, bạn sẽ tạo một Public Subnet nằm trong VPC `TodoVPC`. Subnet này sẽ cho phép EC2 của bạn truy cập internet thông qua IP công cộng.
{{% /notice %}}

---

## 🌐 Tạo Public Subnet `TodoPublicSubnet`

### 1. Truy cập Subnet Console

- Truy cập [VPC Console](https://console.aws.amazon.com/vpc/home)
- Chọn **Subnets** từ menu bên trái
- Click **Create subnet**

![Subnet](/images/2.prerequisite/003-create-subnet.png)

---

### 2. Cấu hình Subnet

Tại trang **Create subnet**:

| Trường                | Giá trị                         |
|------------------------|----------------------------------|
| **VPC ID**             | Chọn `TodoVPC`                 |
| **Subnet name**        | `TodoPublicSubnet`             |
| **Availability Zone**  | ap-southeast-1a (hoặc AZ đầu tiên) |
| **IPv4 CIDR block**    | `10.10.1.0/24`                 |

→ Click **Create subnet**

![Subnet](/images/2.prerequisite/004-create-subnet.png)

---

### 3. Bật Public IP tự động

Sau khi tạo xong:

- Chọn subnet `TodoPublicSubnet` trong danh sách
- Click **Actions** → **Edit subnet settings**

![Subnet](/images/2.prerequisite/005-edit-subnet-setting.png)

- Tại mục **Auto-assign IPv4**, chọn `Enable`
- Click **Save**

![Subnet](/images/2.prerequisite/006-enable-public-ip.png)

---

## ✅ Kết quả mong đợi

- Tạo thành công `TodoPublicSubnet` với CIDR `10.10.1.0/24`
- Tự động cấp phát Public IP cho các EC2 nằm trong subnet này
