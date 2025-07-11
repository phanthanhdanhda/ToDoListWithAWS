---
title: "Deploy application on EC2"
date: 2025-07-10
weight: 1
chapter: false
pre: "<b>3.1</b>"
---

{{% notice info %}}
In this section, you will set up the Node.js application to run in the background using PM2, ensuring the application remains running even if the EC2 instance is rebooted.
{{% /notice %}}

---

## 1. SSH into EC2

From your computer, open a terminal and run the following command (make sure you are in the directory containing the `.pem` file):

```bash
ssh -i LabKeypair.pem ubuntu@<EC2_PUBLIC_IP>
```

## 2. Install PM2

PM2 is a process manager that helps manage Node.js applications running in the background:

```bash
npm install -g pm2
```

### Check installation:

```bash
pm2 --version
```

## 3. Start the application with PM2

### 1. Move to the application directory:

```bash
cd ~/todo-app
```

### 2. Start the application with PM2:

```bash
pm2 start app.js --name todo-app
```

### 3. Check status:

```bash
pm2 list
```

You will see output similar to:

```
┌─────┬──────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
│ id  │ name     │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
├─────┼──────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
│ 0   │ todo-app │ default     │ 1.0.0   │ fork    │ 12345    │ 2s     │ 0    │ online    │ 0%       │ 25.2mb   │ ubuntu   │ disabled │
└─────┴──────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
```

## 4. Set up auto-start after reboot

### 1. Create a startup script:

```bash
pm2 startup
```

### 2. The above command will print a line like (example):

```bash
sudo env PATH=$PATH:/home/ubuntu/.nvm/versions/node/v20.5.0/bin \
pm2 startup systemd -u ubuntu --hp /home/ubuntu
```

### 3. Copy and run that line in the terminal.

### 4. Save the current state:

```bash
pm2 save
```

## 5. Check after reboot (optional)

### 1. Try rebooting EC2:

```bash
sudo reboot
```

### 2. After EC2 restarts, SSH back in:

```bash
ssh -i LabKeypair.pem ubuntu@<EC2_PUBLIC_IP>
```

### 3. Check PM2:

```bash
pm2 list
```

The `todo-app` application should still be running.

### 4. Test the application:

```bash
curl http://localhost:3000
```

## 6. Useful PM2 commands

### Process management:

```bash
# View realtime logs
pm2 logs todo-app

# Restart application
pm2 restart todo-app

# Stop application
pm2 stop todo-app

# View detailed info
pm2 show todo-app

# Monitoring dashboard
pm2 monit
```

### Troubleshooting:

```bash
# If the application does not start
pm2 logs todo-app --lines 50

# Check if the file exists
ls -la ~/todo-app/app.js

# Check if port is in use
sudo netstat -tlnp | grep :3000
```

## 7. Check the application from browser

### 1. Make sure the Security Group has opened port 3000:
- Go to AWS Console → EC2 → Security Groups
- Add Inbound Rule: Type: Custom TCP, Port: 3000, Source: 0.0.0.0/0

### 2. Access the application:

```
http://<EC2_PUBLIC_IP>:3000
```

## Expected results

- ✅ Application runs stably with PM2
- ✅ Automatically restarts after reboot
- ✅ Can be accessed from browser
- ✅ Logs are managed by PM2

{{% notice success %}}
💡 **Congratulations!** You have completed deploying the Node.js application as a background service on EC2 using PM2.
{{% /notice %}}

{{% notice tip %}}
To optimize for production, consider using a reverse proxy like Nginx and an SSL certificate for HTTPS.
{{% /notice %}}