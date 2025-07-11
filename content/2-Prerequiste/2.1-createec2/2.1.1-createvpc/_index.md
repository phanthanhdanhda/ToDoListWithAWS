---
title: "Create VPC"
date: 2025-07-10
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

{{% notice info %}}
In this step, you will create a Virtual Private Cloud (VPC) named `TodoVPC` to contain the entire network infrastructure for the application.
{{% /notice %}}

---

## 🧭 Steps

### 1. Access the VPC Console

- Go to: [VPC Console](https://console.aws.amazon.com/vpc/home)
- Select **Your VPCs**
- Click **Create VPC**

![VPC](/images/2.prerequisite/001-createvpc.png)

---

### 2. Configure VPC information

At the **Create VPC** screen:

| Field                | Value                  |
|----------------------|------------------------|
| **Name tag**         | `TodoVPC`              |
| **IPv4 CIDR block**  | `10.10.0.0/16`         |
| **Tenancy**          | default                |

Keep the remaining options unchanged → Click **Create VPC**

![VPC](/images/2.prerequisite/002-createvpc.png)

---

### 3. Check status

After creation, check the VPCs list to ensure that VPC `TodoVPC` has **available** status.

---

## ✅ Expected Results

- Successfully created VPC `TodoVPC` with a private IP range
- Ready to create subnets and other network components inside the VPC
