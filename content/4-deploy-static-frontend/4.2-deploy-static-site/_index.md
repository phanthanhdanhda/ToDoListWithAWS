---
title: "Deploy static site to S3"
date: 2025-05-25
weight: 2
chapter: false
pre: "<b> 4.2 </b>"
---

## Deploy static site to S3

In this step, you will upload the static interface (HTML, CSS, JS) of the To-do List application to an S3 bucket to make it public on the web.

---

### 📁 Step 1: Prepare the frontend source code

1. Open the To-do List project folder
2. Go to the folder containing the frontend (e.g. `public/` or `frontend/`)
3. Make sure you have `index.html` and other necessary static files (style.css, script.js, etc.)

---

### ☁️ Step 2: Upload the frontend to S3

#### Method 1: Using AWS CLI (recommended)

```bash
aws s3 sync ./public s3://todo-frontend-<your-name> --acl public-read
```

{{% notice tip %}}
./public: the folder containing the frontend files

Replace <your-name> with your actual bucket name
{{% /notice %}}

#### Method 2: Using AWS S3 Console

1. Go to the bucket you created
2. Click **Upload** → **Add files** or **Add folder**

![S3](/images/4-deploy-static-frontend/005-upload-bucket.png)

3. Select all frontend content (index.html, assets, etc.)
4. Click **Upload**

---

### 🌐 Step 3: Enable Static Website Hosting

1. In the bucket → **Properties** tab

![S3](/images/4-deploy-static-frontend/006-static-host.png)

2. Scroll down to **Static website hosting**
3. Click **Edit**

![S3](/images/4-deploy-static-frontend/007-static-host.png)

4. Select **Enable**

![S3](/images/4-deploy-static-frontend/008-static-host.png)

5. Enter:
   - **Index document**: index.html
   - (Optional) **Error document**: 404.html

![S3](/images/4-deploy-static-frontend/009-static-host.png)

6. Click **Save changes**

---

### 🧪 Step 4: Access the website

After enabling Static website hosting, you will see the **Bucket website endpoint**

![S3](/images/4-deploy-static-frontend/010-bucket-website.png)

Click that link or copy and paste it into your browser

{{% notice tip %}}
📌 Example: http://todo-frontend-yourname.s3-website-ap-southeast-1.amazonaws.com
{{% /notice %}}

{{% notice success %}}
✅ The To-do List frontend has been successfully deployed on S3.
{{% /notice %}}

Next, we will configure CloudFront to accelerate and provide a nice domain.