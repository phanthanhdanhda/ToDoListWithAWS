---
title: "Create Internet Gateway and Route Table"
date: 2025-05-25
weight: 3
chapter: false
pre: " <b> 2.1.3 </b> "
---

{{% notice info %}}
In this step, you will create an **Internet Gateway** and **Route Table**, then attach them to the subnet so that EC2 can access the Internet.
{{% /notice %}}

---

## 🌐 Create Internet Gateway `TodoIGW`

### 1. Access Console

- Go to [VPC Console](https://console.aws.amazon.com/vpc/home)
- Select **Internet Gateways** → Click **Create internet gateway**

![IGW](/images/2.prerequisite/007-create-igw.png)

### 2. Configure IGW

| Field        | Value      |
|--------------|------------|
| **Name tag** | `TodoIGW`  |

→ Click **Create internet gateway**

![IGW](/images/2.prerequisite/008-create-igw.png)

---

### 3. Attach IGW to VPC

- Select the newly created `TodoIGW`
- Click **Actions** → **Attach to VPC**

![IGW](/images/2.prerequisite/009-attach-igw.png)

- Select VPC: `TodoVPC` → Click **Attach**

![IGW](/images/2.prerequisite/010-attach-igw.png)

---

## 📡 Create Route Table `TodoPublicRTB`

### 4. Create a new Route Table

- Go back to **VPC Console**
- Select **Route Tables** → Click **Create route table**

![Route Table](/images/2.prerequisite/011-create-rtb.png)

| Field         | Value           |
|---------------|-----------------|
| **Name tag**  | `TodoPublicRTB` |
| **VPC**       | `TodoVPC`       |

→ Click **Create route table**

---

## 🔁 Add Internet Route and Assign Subnet

### 5. Add route to Internet

- Select the newly created `TodoPublicRTB`
- Tab **Routes** → Click **Edit routes** → **Add route**

![Route Table](/images/2.prerequisite/012-create-rtb.png)

| Field         | Value                |
|---------------|----------------------|
| **Destination** | `0.0.0.0/0`        |
| **Target**      | `TodoIGW` (Internet Gateway) |

→ Click **Save changes**

![Route](/images/2.prerequisite/013-add-route.png)

---

### 6. Associate with Public Subnet

- Tab **Subnet associations** → Click **Edit subnet associations**

![Route Subnet](/images/2.prerequisite/014-subnet-association.png)

- Tick: `TodoPublicSubnet` → Click **Save associations**

![Route Subnet](/images/2.prerequisite/015-subnet-association.png)

---

{{% notice tip %}}
✅ After this step, EC2 in the `TodoPublicSubnet` can access the Internet.
{{% /notice %}}

{{% notice tip %}}
🔧 **Note**: Make sure the `TodoPublicSubnet` has **Auto-assign IPv4** enabled in step **2.1.2** so EC2 receives a public IP.
{{% /notice %}}