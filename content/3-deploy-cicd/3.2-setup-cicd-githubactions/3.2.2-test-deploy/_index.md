---
title: "Push code and verify deployment"
date: 2025-07-10
weight: 2
chapter: false
pre: " <b> 3.2.2 </b> "
---

## Push code and check the workflow

After creating the CI/CD workflow file, you can test it by pushing to GitHub.

---

### 🚀 Step 1: Push code to GitHub

```bash
git add .
git commit -m "Set up CI/CD deploy with GitHub Actions"
git push origin main
```

---

### 📦 Step 2: Check the workflow on GitHub

1. Go to your GitHub repository
2. Open the **Actions** tab

![Act](/images/3.deploy/004-github-action.png)

3. Select the **Deploy To EC2** workflow

![Sec](/images/3.deploy/005-github-action.png)

4. Check the execution steps:
   - Connect to EC2
   - Pull code
   - Run npm install
   - Restart the application with PM2

---

### 🌐 Step 3: Access the application

Open your browser and go to:

```
http://<EC2_PUBLIC_IP>:3000
```

If everything is correct, you will see the To-do List web interface working properly after each code push.

{{% notice tip %}}
You should check pm2 logs on EC2 if the application does not respond after deployment.
{{% /notice %}}