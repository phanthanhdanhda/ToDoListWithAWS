---
title: "Triển khai ứng dụng To-do List trên AWS"
date: 2025-07-10
weight: 1
chapter: true
---

## Mục tiêu của Workshop

Trong workshop này, bạn sẽ học cách triển khai một ứng dụng web **To-do List** thực tế sử dụng **Node.js** và **MongoDB** trên **hạ tầng AWS**. Quá trình triển khai tuân theo tư duy DevOps: tự động hóa, kiểm thử, CI/CD và vận hành thực tế.

{{% notice tip %}}
Đây là một dự án thực hành DevOps hoàn chỉnh từ đầu đến cuối, giúp bạn kết nối giữa coding và vận hành.
{{% /notice %}}

---

## Yêu cầu

- Tài khoản AWS có quyền tạo EC2, VPC, S3, IAM, và CloudFront.
- Kiến thức cơ bản về SSH, Linux, Git.
- Đã cài đặt công cụ: Git, SSH client, trình duyệt.

{{% notice warning %}}
Bạn sẽ phát sinh chi phí khi triển khai trên AWS. Hãy đảm bảo bạn có quyền truy cập và theo dõi billing.
{{% /notice %}}

---

## Tổng quan nội dung

1. **Giới thiệu**  
   Giới thiệu tổng quan về dự án To-do List và kiến trúc triển khai trên AWS.

2. **Các bước chuẩn bị**  
   Tạo EC2, cài đặt môi trường, kiểm thử ứng dụng To-do List chạy local trên server.

3. **Triển khai dịch vụ AWS**  
   Cấu hình domain, S3, CloudFront, gắn ứng dụng public.

4. **Thiết lập CI/CD với GitHub Actions**  
   Tự động build & deploy mỗi lần push source.

5. **Quản trị & Giải phóng tài nguyên**  
   Theo dõi, tối ưu và dọn dẹp tài nguyên sau khi sử dụng.

---

## Kiến trúc triển khai

![Arch](/images/arc-logical.png)

Ứng dụng được chia làm hai phần:

- **Backend Node.js**: chạy trên EC2, kết nối MongoDB cài đặt local.
- **Frontend tĩnh**: build React app & deploy lên S3 + CloudFront.

{{% notice info %}}
Đây là kiến trúc đơn giản nhưng thực tế, giúp bạn tiếp cận nhanh chóng các dịch vụ cốt lõi của AWS.
{{% /notice %}}
