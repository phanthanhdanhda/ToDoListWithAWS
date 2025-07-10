---
title: "Create CI/CD workflow file"
date: 2025-05-25
weight: 1
chapter: false
pre: "<b>3.2.1</b>"
---

## Create GitHub Actions workflow

We will create a simple workflow to:
- **SSH** into **EC2**.
- **Pull new code** from **GitHub**.
- Install **dependencies** and restart the application with **PM2**.

---

### 🛠️ Step 1: Create the `.github/workflows` directory

At the root of your Node.js project, create the following structure:

```bash
mkdir -p .github/workflows
```

---

### 📝 Step 2: Create the `deploy.yml` file

Create the file `.github/workflows/deploy.yml` with the following content:

```yaml
name: Deploy To EC2

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Deploy to EC2 via SSH
      uses: appleboy/ssh-action@v0.1.10
      with:
        host: ${{ secrets.EC2_HOST }}
        username: ${{ secrets.EC2_USER }}
        key: ${{ secrets.EC2_KEY }}
        script: |
          cd todo-app
          git pull origin main
          npm install
          pm2 restart all || pm2 start index.js --name todo
```

---

### 🔐 Step 3: Create GitHub Secrets

On your GitHub repository page:

1. Go to **Settings → Secrets and variables → Actions**.

![Sec](/images/3.deploy/001-github-secret.png)

2. Click **New repository secret**.

![Sec](/images/3.deploy/002-github-secret.png)

3. Create the following variables:

| Variable    | Description                        |
| ----------- | ---------------------------------- |
| `EC2_HOST`  | Public IP of your EC2              |
| `EC2_USER`  | SSH username, e.g. `ubuntu`        |
| `EC2_KEY`   | Content of your `.pem` private key |

![Sec](/images/3.deploy/003-github-secret.png)

---

{{% notice success %}}
✅ After completing these steps, every time you push code to the main branch, the workflow will automatically connect to EC2, pull the new code, and restart the application with PM2.
{{% /notice %}}