---
title: "Create EC2 Ubuntu Instance"
date: 2025-07-10
weight: 5
chapter: false
pre: " <b> 2.1.5 </b> "
---

### Create EC2 Instance

1. Go to the [EC2 Console](https://console.aws.amazon.com/ec2/v2/home)
   + Click **Launch Instance**

![EC2](/images/2-Prerequiste/019-launch-instance.png)

2. Configure:

| Field              | Value                                 |
|--------------------|---------------------------------------|
| **Name**           | `todo-ubuntu`                         |
| **AMI**            | Ubuntu Server 22.04 LTS (64-bit)      |
| **Instance type**  | `t2.micro`                            |
| **Key pair**       | Select or create a new one            |
| **Network**        | `TodoVPC`                             |
| **Subnet**         | `TodoPublicSubnet`                    |
| **Auto-assign IP** | Enable                                |
| **Security Group** | `TodoSG`                              |

![EC2](/images/2-Prerequiste/020-config-ec2.png)

![EC2](/images/2-Prerequiste/021-config-ec2.png)

{{% notice tip %}}
💡 Make sure the `TodoPublicSubnet` has **Auto-assign IPv4** enabled so the EC2 instance receives a public IP, allowing you to SSH and access the web app easily.
{{% /notice %}}

3. Click **Launch Instance** to create

![EC2](/images/2-Prerequiste/022-config-ec2.png)

---

✅ After this step, the EC2 instance is ready for SSH and application installation.
