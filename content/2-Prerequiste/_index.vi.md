---
title: "Các bước chuẩn bị"
date: 2025-07-10
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

{{% notice info %}}
Trong phần này, bạn sẽ chuẩn bị hạ tầng cần thiết để triển khai ứng dụng web **To-do List** sử dụng **Node.js** và **MongoDB** (cài đặt local) trên EC2.
{{% /notice %}}

---

## 📦 Nội dung

Phần chuẩn bị bao gồm **2 bước chính**:

---

### 🏗️ [2.1. Tạo hạ tầng mạng và EC2 Instance](2.1-createec2/)

Bạn sẽ tạo các thành phần cần thiết:

- ✅ **VPC riêng biệt** với 2 subnet: public và private
- ✅ **Security Group** mở cổng 22 và 3000 cho EC2
- ✅ **EC2 Instance** chạy Ubuntu làm backend server (MongoDB local)

---

### ⚙️ [2.2. Cài đặt môi trường ứng dụng trên EC2](2.2-installenvironment/)

Bạn sẽ SSH vào EC2 và thực hiện:

- ✅ Cài **Node.js**, **MongoDB** và các công cụ phụ trợ
- ✅ Clone source code To-do List từ GitHub
- ✅ Kiểm tra ứng dụng chạy trên cổng **3000** thông qua IP public

---

## 🎯 Kết quả mong đợi

Sau khi hoàn thành phần này, bạn sẽ có:

- ✅ EC2 instance đang chạy Ubuntu
- ✅ Đầy đủ Node.js và MongoDB
- ✅ Ứng dụng To-do List chạy được qua public IP
- ✅ Môi trường sẵn sàng cho các bước tiếp theo

---

{{% notice tip %}}
💡 **Lưu ý**: Một số bước như cài đặt Node.js, MongoDB hoặc SSH không phải là dịch vụ AWS, nhưng rất quan trọng để triển khai ứng dụng thực tế, vì vậy vẫn được đưa vào workshop này.
{{% /notice %}}
