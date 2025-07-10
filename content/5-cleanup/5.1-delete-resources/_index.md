---
title: "Delete EC2, S3, CloudFront, Security Group & Key Pair"
date: 2025-05-25
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

In this step, you will delete the following resources:

- EC2 Instance
- Security Group
- S3 Bucket
- CloudFront Distribution
- Key Pair (if no longer needed)

---

### 🧹 1. Delete EC2 Instance

1. Go to [EC2 Console](https://console.aws.amazon.com/ec2/v2/home)
2. Select the instance named `To-do EC2`
3. Click **Instance State → Terminate instance**
4. Confirm

---

### 🧹 2. Delete Security Group

1. Go to the **Security Groups** menu (in EC2 or VPC)
2. Delete the security group named `TodoSG`

> 💡 If the security group is still attached to an EC2 or other resource, you need to detach it before deleting.

---

### 🧹 3. Delete Key Pair

1. Go to [EC2 → Key Pairs](https://console.aws.amazon.com/ec2/v2/home?#KeyPairs)
2. If you created `LabKeypair` or similar just for practice, you can delete it.

---

### 🧹 4. Delete S3 Bucket

1. Go to [S3 Console](https://s3.console.aws.amazon.com/s3)
2. Select the bucket containing the static site (e.g. `todo-frontend-bucket`)
3. Click **Empty** first → then **Delete bucket**

---

### 🧹 5. Delete CloudFront Distribution

1. Go to [CloudFront Console](https://console.aws.amazon.com/cloudfront)
2. Select the distribution you created → **Disable**
3. After the status is **Disabled**, click **Delete**

> ⚠️ CloudFront may take a few minutes to change to Disabled status before you can delete it.