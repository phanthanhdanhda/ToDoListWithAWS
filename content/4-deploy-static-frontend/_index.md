---
title: "Deploy static frontend with S3 and CloudFront"
date: 2025-05-25
weight: 4
chapter: true
pre: "<b> 4. </b>"
---

{{% notice info %}}
In this chapter, you will deploy the static web interface (HTML/CSS/JS) of the To-do List application to Amazon S3, then use CloudFront to distribute the content via CDN.
{{% /notice %}}

---

### ✅ Objectives

- Create an S3 bucket to store the static site
- Configure the bucket for public access
- Deploy the frontend via AWS CLI or console
- Create a CloudFront Distribution to deliver the website globally

---

### 📚 Content

- [Create S3 Bucket for frontend](4.1-setup-s3/)
- [Deploy static site to S3](4.2-deploy-static-site/)
- [Configure CloudFront for content delivery](4.3-setup-cloudfront/)