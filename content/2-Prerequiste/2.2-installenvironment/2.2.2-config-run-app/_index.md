---
title: "Configure application and test run"
date: 2025-05-25
weight: 2
chapter: false
pre: "<b>2.2.2</b>"
---

## Clone source code

### 1. Create project directory:

```bash
mkdir -p ~/todo-app && cd ~/todo-app
```

### 2. Clone source code from GitHub:

```bash
git clone https://github.com/your-username/todo-list-app.git .
```

### 3. Install dependencies:

```bash
npm install
```

## Configure .env (if needed)

### 1. Create .env file if not exists:

```bash
touch .env
```

### 2. Add local MongoDB configuration:

```env
MONGO_URI=mongodb://localhost:27017/todoapp
PORT=3000
```

## Test run application

### 1. Run application:

```bash
node app.js
```

### 2. Access browser and enter:

```
http://<EC2_PUBLIC_IP>:3000
```

### 3. Check if the To-do List web interface is displayed.

{{% notice tip %}}
If you cannot access, please check:
- Port 3000 is open in Security Group
- Service has been started successfully
- IP address is the correct public IP of EC2 instance
{{% /notice %}}
