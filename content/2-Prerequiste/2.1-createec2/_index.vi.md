---
title: "Tạo hạ tầng mạng và EC2 Instance"
date: 2025-05-25
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

{{% notice info %}}
Trong phần này, bạn sẽ tạo các thành phần hạ tầng cơ bản để triển khai ứng dụng: VPC, Subnet, Internet Gateway, Route Table, Security Group và một EC2 instance chạy Ubuntu.
{{% /notice %}}

---

## Nội dung

- [Tạo VPC](/2-prerequisite/2.1-createec2/2.1.1-createvpc/)
- [Tạo Subnet](/2-prerequisite/2.1-createec2/2.1.2-createpublicsubnet/)
- [Tạo Internet Gateway và Route Table](/2-prerequisite/2.1-createec2/2.1.3-create-igw-rtb/)
- [Tạo Security Group](/2-prerequisite/2.1-createec2/2.1.4-create-security-group/)
- [Tạo EC2 Instance Ubuntu](/2-prerequisite/2.1-createec2/2.1.5-create-ec2-ubuntu/)

---

## Kết quả mong đợi

Sau khi hoàn thành phần này, bạn sẽ có:

- ✅ Một VPC riêng biệt tên `TodoVPC`
- ✅ Một subnet public tên `TodoPublicSubnet`
- ✅ Kết nối internet qua Internet Gateway và Route Table
- ✅ Security Group mở cổng SSH (22) và app (3000)
- ✅ EC2 Ubuntu sẵn sàng SSH và cài ứng dụng

---

{{% notice tip %}}
💡 Nếu bạn đã từng tạo các thành phần này trước đây, có thể tận dụng lại để tiết kiệm thời gian. Tuy nhiên, nên thực hành đầy đủ để nắm vững quy trình triển khai hạ tầng AWS.
{{% /notice %}}
