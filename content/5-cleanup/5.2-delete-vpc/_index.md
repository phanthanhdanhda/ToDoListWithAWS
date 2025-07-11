---
title: "Delete VPC and related components"
date: 2025-07-10
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

After deleting all EC2 instances, you can delete the custom VPC and its related components:

---

### 🧹 1. Delete Subnet

1. Go to [VPC Console](https://console.aws.amazon.com/vpc)
2. Select **Subnets** → Delete `TodoPublicSubnet` if no longer used

---

### 🧹 2. Delete Internet Gateway

1. Select **Internet Gateways**
2. **Detach** from VPC if attached → then **Delete**

---

### 🧹 3. Delete Route Table

1. Select **Route Tables**
2. Select the custom route table → **Delete**

---

### 🧹 4. Delete VPC

1. Go to **Your VPCs**
2. Select `TodoVPC` → click **Delete**

---

> ✅ After completing these steps, you have released all AWS resources used in this workshop.