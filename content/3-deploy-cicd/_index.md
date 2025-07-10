---
title: "Deploy backend and CI/CD"
date: 2025-05-25
weight: 3
chapter: true
pre: "<b> 3. </b>"
---

{{% notice info %}}
This chapter guides you to deploy the Node.js (To-do List) application on EC2 and set up CI/CD using GitHub Actions for automatic deployment on every change.
{{% /notice %}}

---

### Objectives:

- Deploy the application automatically with a script when EC2 starts
- Set up a reverse proxy with Nginx to serve the application on port 80
- Configure proper firewall rules
- Automate backend deployment with GitHub Actions

---

### Content

- [Deploy Node.js application to EC2](3.1-deploy-on-ec2/)
- [Set up CI/CD with GitHub Actions](3.2-setup-cicd-githubactions/)