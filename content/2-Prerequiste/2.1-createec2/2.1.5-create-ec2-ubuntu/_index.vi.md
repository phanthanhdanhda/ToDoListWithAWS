---
title: "Tạo EC2 Ubuntu Instance"
date: 2025-05-25
weight: 5
chapter: false
pre: " <b> 2.1.5 </b> "
---

### Tạo EC2 Instance

1. Truy cập [EC2 Console](https://console.aws.amazon.com/ec2/v2/home)
   + Click **Launch Instance**

![EC2](/images/2-Prerequiste/019-launch-instance.png)

2. Cấu hình:

| Trường              | Giá trị                             |
|---------------------|--------------------------------------|
| **Name**            | `todo-ubuntu`                       |
| **AMI**             | Ubuntu Server 22.04 LTS (64-bit)    |
| **Instance type**   | `t2.micro`                          |
| **Key pair**        | Chọn hoặc tạo mới                   |
| **Network**         | `TodoVPC`                           |
| **Subnet**          | `TodoPublicSubnet`                  |
| **Auto-assign IP**  | Enable                              |
| **Security Group**  | `TodoSG`                            |

![EC2](/images/2-Prerequiste/020-config-ec2.png)

![EC2](/images/2-Prerequiste/021-config-ec2.png)

{{% notice tip %}}
💡 Đảm bảo subnet `TodoPublicSubnet` đã bật **Auto-assign IPv4** để EC2 nhận IP công cộng, giúp bạn SSH và truy cập web app dễ dàng.
{{% /notice %}}

3. Click **Launch Instance** để tạo

![EC2](/images/2-Prerequiste/022-config-ec2.png)

---

✅ Sau bước này, EC2 instance đã sẵn sàng để SSH và cài đặt ứng dụng.
