---
title: "Configure CloudFront for content delivery"
date: 2025-05-25
weight: 3
chapter: false
pre: "<b> 4.3 </b>"
---

## Configure CloudFront for content delivery

In this step, you will configure **CloudFront** to deliver static content from S3 with faster speed and a more memorable domain name.

---

### 🌐 Step 1: Access CloudFront

1. Open [AWS CloudFront Console](https://console.aws.amazon.com/cloudfront/)
2. Click **Create Distribution**

![CF](/images/4-deploy-static-frontend/011-create-distribution.png)

---

### 📥 Step 2: Configure Origin

In the **Origin Settings** section:

- **Origin domain**: Select the S3 bucket where you enabled Static website hosting  
  ⛔ Do not select the default S3 endpoint type (`s3.amazonaws.com`), choose the one like `s3-website...`
- **Origin access**: Select **Public** (if you are not using OAC)
- **Viewer protocol policy**: Select **Redirect HTTP to HTTPS**

![CF](/images/4-deploy-static-frontend/012-create-distribution.png)

---

### 🛠️ Step 3: Configure default behavior

- **Cache policy**: `CachingOptimized`
- **Response headers policy**: `SecurityHeadersPolicy` (if available)
- **Compress objects automatically**: ✅ Enabled
- Click **Create distribution**

![CF](/images/4-deploy-static-frontend/013-create-distribution.png)

---

### 🕒 Step 4: Wait for CloudFront to be ready

- You will see a status line “In Progress”
- Wait about 5–10 minutes until it changes to **Enabled**

![CF](/images/4-deploy-static-frontend/014-create-distribution.png)

---

### 🔗 Step 5: Access via CloudFront

- In the **Domain name** column, you will see a domain like:

  `d123456abcdef8.cloudfront.net`

![CF](/images/4-deploy-static-frontend/015-create-distribution.png)

- Access that domain to see your frontend in action

![CF](/images/4-deploy-static-frontend/016-create-distribution.png)

---

### ✅ Done

The To-do List frontend has now been distributed globally via CloudFront!

You can use this CloudFront domain to connect the frontend to the API (backend running on EC2).