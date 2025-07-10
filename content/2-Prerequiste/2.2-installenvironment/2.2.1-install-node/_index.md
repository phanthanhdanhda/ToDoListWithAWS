---
title: "Install Node.js and MongoDB"
date: 2025-05-25
weight: 1
chapter: false
pre: "<b>2.2.1</b>"
---

## SSH into EC2

1. Open terminal (PowerShell or bash).
2. SSH into the instance using private key:

```bash
ssh -i ~/path/to/LabKeypair.pem ubuntu@<EC2_PUBLIC_IP>
```

## Install Node.js

### Install Node.js LTS version:

```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Check versions:

```bash
node -v
npm -v
```

## Install MongoDB (local)

### 1. Import GPG key:

```bash
curl -fsSL https://pgp.mongodb.com/server-6.0.asc | \
  sudo gpg -o /usr/share/keyrings/mongodb-server-6.0.gpg \
  --dearmor
```

### 2. Add repository:

```bash
echo "deb [ signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg ] \
https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/6.0 multiverse" | \
sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
```

### 3. Install MongoDB:

```bash
sudo apt update
sudo apt install -y mongodb-org
```

### 4. Start MongoDB service:

```bash
sudo systemctl start mongod
sudo systemctl enable mongod
```

### 5. Check MongoDB status:

```bash
sudo systemctl status mongod
```

{{% notice tip %}}
You are ready to deploy the application after completing this step.
{{% /notice %}}
