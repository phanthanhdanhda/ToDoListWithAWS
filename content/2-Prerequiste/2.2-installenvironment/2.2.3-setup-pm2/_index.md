---
title: "Set up PM2 for background running"
date: 2025-07-10
weight: 3
chapter: false
pre: "<b>2.2.3</b>"
---

## Install PM2

PM2 is a process manager that helps Node.js applications always run in the background and automatically restart when encountering errors or after a system reboot.

### 1. Install PM2:

```bash
npm install -g pm2
```

## Run the application with PM2

### 1. Navigate to the project directory:

```bash
cd ~/todo-app
```

### 2. Start the application with PM2:

```bash
pm2 start app.js --name todo-app
```

### 3. Check status:

```bash
pm2 status
```

## Set up system startup

### 1. Enable PM2 to start with the system:

```bash
pm2 startup
```

### 2. Execute the printed command (example):

```bash
sudo env PATH=$PATH:/home/ubuntu/.nvm/versions/node/v18.17.0/bin \
pm2 startup systemd -u ubuntu --hp /home/ubuntu
```

### 3. Save the process list:

```bash
pm2 save
```

## Verify the application

### 1. Open your browser and go to:

```
http://<EC2_PUBLIC_IP>:3000
```

### 2. If the server reboots, the application will still run thanks to PM2.

## Useful PM2 commands

```bash
# View logs
pm2 logs todo-app

# Restart application
pm2 restart todo-app

# Stop application
pm2 stop todo-app

# Remove application from PM2
pm2 delete todo-app

# View detailed information
pm2 show todo-app
```

{{% notice tip %}}
PM2 also supports logging, automatic restart, cluster mode, and managing multiple applications — very useful for production environments.
{{% /notice %}}
