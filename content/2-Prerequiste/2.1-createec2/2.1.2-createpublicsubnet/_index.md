---
title: "Create Subnet"
date: 2025-05-25
weight: 2
chapter: false
pre: " <b> 2.1.2 </b> "
---

{{% notice info %}}
In this step, you will create a Public Subnet inside the `TodoVPC` VPC. This subnet will allow your EC2 to access the internet via a public IP.
{{% /notice %}}

---

## 🌐 Create Public Subnet `TodoPublicSubnet`

### 1. Access the Subnet Console

- Go to [VPC Console](https://console.aws.amazon.com/vpc/home)
- Select **Subnets** from the left menu
- Click **Create subnet**

![Subnet](/images/2.prerequisite/003-create-subnet.png)

---

### 2. Configure Subnet

At the **Create subnet** page:

| Field                | Value                              |
|----------------------|------------------------------------|
| **VPC ID**           | Select `TodoVPC`                   |
| **Subnet name**      | `TodoPublicSubnet`                 |
| **Availability Zone**| ap-southeast-1a (or the first AZ)  |
| **IPv4 CIDR block**  | `10.10.1.0/24`                     |

→ Click **Create subnet**

![Subnet](/images/2.prerequisite/004-create-subnet.png)

---

### 3. Enable Auto Public IP

After creation:

- Select the `TodoPublicSubnet` subnet in the list
- Click **Actions** → **Edit subnet settings**

![Subnet](/images/2.prerequisite/005-edit-subnet-setting.png)

- In **Auto-assign IPv4**, select `Enable`
- Click **Save**

![Subnet](/images/2.prerequisite/006-enable-public-ip.png)

---

## ✅ Expected Results

- Successfully created `TodoPublicSubnet` with CIDR `10.10.1.0/24`
- Automatic Public IP assignment for EC2s in this subnet