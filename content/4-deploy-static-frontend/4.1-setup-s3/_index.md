---
title: "Create S3 Bucket for frontend"
date: 2025-07-10
weight: 1
chapter: false
pre: "<b> 4.1 </b>"
---

## Create an S3 bucket to store the frontend

In this step, you will create an S3 bucket to store the static interface source code of the To-do List application.

---

### 🔧 Step 1: Access the S3 management console

1. Go to [Amazon S3 Console](https://s3.console.aws.amazon.com/s3/home)
2. Click **Create bucket**

![S3](/images/4-deploy-static-frontend/001-create-bucket.png)

---

### 📥 Step 2: Enter bucket information

- **Bucket name**: a unique name, e.g. `todo-frontend-<your-name>`
- Uncheck **Block all public access** to allow public access
- Check the security warning confirmation

![S3](/images/4-deploy-static-frontend/002-create-bucket.png)

---

### 🛡️ Step 3: Disable public access block

1. After creation, go to the **Permissions** tab
2. Find **Block public access (bucket settings)**
3. Click **Edit**, uncheck all, then **Save**

---

### 🌍 Step 4: Allow public read access

1. Go to **Permissions** tab → **Bucket Policy** → **Edit**

![S3](/images/4-deploy-static-frontend/003-bucket-policy.png)

2. Paste the following policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::todo-frontend-<your-name>/*"
    }
  ]
}
```

3. Click **Save Changes**

![S3](/images/4-deploy-static-frontend/004-bucket-policy.png)

{{% notice tip %}}
📌 Replace <your-name> with the exact bucket name you set.
{{% /notice %}}

{{% notice success %}}
✅ You have successfully created a public S3 bucket to store the frontend.
{{% /notice %}}

Next, we will upload the HTML/CSS/JS source code to this bucket.