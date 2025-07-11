---
title: "Create Security Group"
date: 2025-07-10
weight: 4
chapter: false
pre: " <b> 2.1.4 </b> "
---

### Create Security Group for the application

We will create a new Security Group to open the necessary ports for deploying the To-do List web application on EC2:

- Open port **22** to SSH into the server  
- Open port **3000** to access the web application

---

### Steps

1. Go to [EC2 Console > Security Groups](https://console.aws.amazon.com/ec2/v2/home#SecurityGroups)
   - Click **Create security group**

![SG](/images/2.Prerequiste/016-create-sg.png)

2. Configure:
   - **Security group name**: `TodoSG`
   - **Description**: `Security Group for To-do List App`
   - **VPC**: select `TodoVPC`

![SG](/images/2.Prerequiste/017-create-sg.png)

3. Add **Inbound rules**:
   - Type: SSH | Protocol: TCP | Port: 22 | Source: `My IP`
   - Type: Custom TCP | Protocol: TCP | Port: 3000 | Source: `0.0.0.0/0`

![SG](/images/2.Prerequiste/018-create-sg.png)

{{% notice tip %}}
💡 Open port **3000** to the entire internet because your application will run on this port. You can restrict the IP if you only need internal access.
{{% /notice %}}

4. Keep **Outbound rule (Allow all traffic)** unchanged

5. Click **Create security group**

---

✅ After this step, you have the `TodoSG` Security Group ready to assign to EC2 in the next step.