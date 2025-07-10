---
title: "Tạo Internet Gateway và Route Table"
date: 2025-05-25
weight: 3
chapter: false
pre: " <b> 2.1.3 </b> "
---

{{% notice info %}}
Trong bước này, bạn sẽ tạo **Internet Gateway** và **Route Table**, sau đó gắn với subnet để EC2 có thể truy cập Internet.
{{% /notice %}}

---

## 🌐 Tạo Internet Gateway `TodoIGW`

### 1. Truy cập Console

- Truy cập [VPC Console](https://console.aws.amazon.com/vpc/home)
- Chọn **Internet Gateways** → Click **Create internet gateway**

![IGW](/images/2.prerequisite/007-create-igw.png)

### 2. Cấu hình IGW

| Trường      | Giá trị     |
|-------------|--------------|
| **Name tag** | `TodoIGW`   |

→ Click **Create internet gateway**

![IGW](/images/2.prerequisite/008-create-igw.png)

---

### 3. Gắn IGW vào VPC

- Chọn `TodoIGW` mới tạo
- Click **Actions** → **Attach to VPC**

![IGW](/images/2.prerequisite/009-attach-igw.png)

- Chọn VPC: `TodoVPC` → Click **Attach**

![IGW](/images/2.prerequisite/010-attach-igw.png)

---

## 📡 Tạo Route Table `TodoPublicRTB`

### 4. Tạo Route Table mới

- Truy cập lại **VPC Console**
- Chọn **Route Tables** → Click **Create route table**

![Route Table](/images/2.prerequisite/011-create-rtb.png)

| Trường         | Giá trị       |
|----------------|----------------|
| **Name tag**   | `TodoPublicRTB` |
| **VPC**        | `TodoVPC`      |

→ Click **Create route table**

---

## 🔁 Thêm Route Internet và Gán Subnet

### 5. Thêm route tới Internet

- Chọn `TodoPublicRTB` mới tạo
- Tab **Routes** → Click **Edit routes** → **Add route**

![Route Table](/images/2.prerequisite/012-create-rtb.png)

| Trường        | Giá trị          |
|---------------|-------------------|
| **Destination** | `0.0.0.0/0`     |
| **Target**     | `TodoIGW` (Internet Gateway) |

→ Click **Save changes**

![Route](/images/2.prerequisite/013-add-route.png)

---

### 6. Gán với Public Subnet

- Tab **Subnet associations** → Click **Edit subnet associations**

![Route Subnet](/images/2.prerequisite/014-subnet-association.png)

- Tick chọn: `TodoPublicSubnet` → Click **Save associations**

![Route Subnet](/images/2.prerequisite/015-subnet-association.png)

---

{{% notice tip %}}
✅ Sau bước này, EC2 trong subnet `TodoPublicSubnet` sẽ có thể truy cập Internet.
{{% /notice %}}

{{% notice tip %}}
🔧 **Ghi chú**: Đảm bảo subnet `TodoPublicSubnet` đã được cấu hình bật **Auto-assign IPv4** ở bước **2.1.2**, để EC2 nhận được IP công cộng.
{{% /notice %}}

