---
title: "Prerequisites"
date: 2025-05-25
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

{{% notice info %}}
In this section, you will prepare the necessary infrastructure to deploy the **To-do List** web application using **Node.js** and **MongoDB (local)** on EC2.
{{% /notice %}}

---

## 📦 Content

The preparation consists of **2 main steps**:

---

### 🏗️ [2.1. Create network infrastructure and EC2 Instance](2.2-createec2/)

You will create the following components:

- ✅ **Dedicated VPC** with 2 subnets: public and private
- ✅ **Security Group** opening ports 22 and 3000 for EC2
- ✅ **EC2 Instance** running Ubuntu as backend server (local MongoDB)

---

### ⚙️ [2.2. Install application environment on EC2](2.2-installenvironment/)

You will SSH into EC2 and perform:

- ✅ Install **Node.js**, **MongoDB**, and supporting tools
- ✅ Clone To-do List source code from GitHub
- ✅ Test the application running on **port 3000** via public IP

---

## 🎯 Expected Results

After completing this section, you will have:

- ✅ EC2 instance running Ubuntu
- ✅ Node.js and MongoDB fully installed
- ✅ To-do List application running via public IP
- ✅ Environment ready for the next steps

---

{{% notice tip %}}
💡 **Note**: Some steps like installing Node.js, MongoDB, or SSH are not AWS services, but are very important for real-world application deployment, so they are included in this workshop.
{{% /notice %}}
