---
title: "Deploy To-do List Application on AWS"
date: 2025-05-25
weight: 1
chapter: true
---

## Workshop Objectives

In this workshop, you will learn how to deploy a real **To-do List** web application using **Node.js** and **MongoDB** on **AWS infrastructure**. The deployment process follows DevOps thinking: automation, testing, CI/CD, and real-world operations.

{{% notice tip %}}
This is a complete hands-on DevOps project from start to finish, helping you bridge the gap between coding and operations.
{{% /notice %}}

---

## Requirements

- AWS account with permissions to create EC2, VPC, S3, IAM, and CloudFront.
- Basic knowledge of SSH, Linux, Git.
- Installed tools: Git, SSH client, web browser.

{{% notice warning %}}
You may incur costs when deploying on AWS. Make sure you have access and monitor billing.
{{% /notice %}}

---

## Content Overview

1. **Introduction**  
   Overview of the To-do List project and deployment architecture on AWS.

2. **Prerequisites**  
   Create EC2, install environment, test To-do List application running locally on server.

3. **Deploy AWS Services**  
   Configure domain, S3, CloudFront, attach public application.

4. **Set up CI/CD with GitHub Actions**  
   Automatically build & deploy on each source push.

5. **Management & Resource Cleanup**  
   Monitor, optimize and clean up resources after use.

---

## Deployment Architecture

![Arch](/images/arc-logical.png)

The application is divided into two parts:

- **Node.js Backend**: runs on EC2, connects to locally installed MongoDB.
- **Static Frontend**: build React app & deploy to S3 + CloudFront.

{{% notice info %}}
This is a simple but practical architecture, helping you quickly get hands-on with core AWS services.
{{% /notice %}}