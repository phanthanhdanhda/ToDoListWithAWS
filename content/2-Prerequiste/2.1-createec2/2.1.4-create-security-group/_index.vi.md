---
title: "Tạo Security Group"
date: 2025-07-10
weight: 4
chapter: false
pre: " <b> 2.1.4 </b> "
---

### Tạo Security Group cho ứng dụng

Chúng ta sẽ tạo một Security Group mới để mở các port cần thiết cho việc triển khai ứng dụng web To-do List trên EC2:

- Mở port **22** để SSH vào server  
- Mở port **3000** để truy cập ứng dụng web

---

### Các bước thực hiện

1. Truy cập [EC2 Console > Security Groups](https://console.aws.amazon.com/ec2/v2/home#SecurityGroups)
   - Click **Create security group**

![SG](/images/2-Prerequiste/016-create-sg.png)

2. Cấu hình:
   - **Security group name**: `TodoSG`
   - **Description**: `Security Group for To-do List App`
   - **VPC**: chọn `TodoVPC`

![SG](/images/2-Prerequiste/017-create-sg.png)

3. Thêm **Inbound rules**:
   - Type: SSH | Protocol: TCP | Port: 22 | Source: `My IP`
   - Type: Custom TCP | Protocol: TCP | Port: 3000 | Source: `0.0.0.0/0`

![SG](/images/2-Prerequiste/018-create-sg.png)

{{% notice tip %}}
💡 Mở port **3000** cho toàn bộ internet vì ứng dụng của bạn sẽ chạy trên cổng này. Bạn có thể giới hạn IP nếu chỉ cần truy cập nội bộ.
{{% /notice %}}

4. Giữ nguyên **Outbound rule (Allow all traffic)**

5. Click **Create security group**

---

✅ Sau bước này, bạn đã có Security Group `TodoSG` sẵn sàng gán cho EC2 ở bước tiếp theo.
