---
title: "Create Network Infrastructure and EC2 Instance"
date: 2025-05-25
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

{{% notice info %}}
In this section, you will create the basic infrastructure components needed to deploy the application: VPC, Subnet, Internet Gateway, Route Table, Security Group, and an EC2 instance running Ubuntu.
{{% /notice %}}

---

## Contents

- [Create VPC](/2-prerequisite/2.1-createec2/2.1.1-createvpc/)
- [Create Subnet](/2-prerequisite/2.1-createec2/2.1.2-createpublicsubnet/)
- [Create Internet Gateway and Route Table](/2-prerequisite/2.1-createec2/2.1.3-create-igw-rtb/)
- [Create Security Group](/2-prerequisite/2.1-createec2/2.1.4-create-security-group/)
- [Create Ubuntu EC2 Instance](/2-prerequisite/2.1-createec2/2.1.5-create-ec2-ubuntu/)

---

## Expected Results

After completing this section, you will have:

- ✅ A dedicated VPC named `TodoVPC`
- ✅ A public subnet named `TodoPublicSubnet`
- ✅ Internet connectivity via Internet Gateway and Route Table
- ✅ A Security Group allowing SSH (22) and app (3000) ports
- ✅ An Ubuntu EC2 instance ready for SSH and application setup

---

{{% notice tip %}}
💡 If you have previously created these components, you can reuse them to save time. However, it is recommended to go through the full practice to thoroughly understand the AWS infrastructure deployment process.
{{% /notice %}}