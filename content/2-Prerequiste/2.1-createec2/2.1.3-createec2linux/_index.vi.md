---
title : "Tạo Public Linux EC2"
date: "2025-06-14"
weight : 5
chapter : false
pre : " <b> 2.1.3 </b> "
---

1. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home)
  + Chọn **Instances**.
  + Chọn **Launch instances**.
  
![EC2](/images/2.prerequisite/EC2_1.png)

2. Tại trang **Launch an instance**.
  + Ở mục **Name and tags** điền **OrderAPI-EC2**.
  + Tại mục **Application and OS Images (Amazon Machine Image)**, Click chọn **Amazon Linux**.
  
![EC2](/images/2.prerequisite/EC2_2.png)

3. Tại mục **Instance type**.
 + Click chọn **t2.micro**.
 
![EC2](/images/2.prerequisite/EC2_3.png)

4. Tạo KeyPair.
  + Tại mục **Key pair name - required ** chọn **Create new key pair**.

![EC2](/images/2.prerequisite/EC2_4.png)

5. Tại giao diện **Create key pair.
  + **Key pair name** điền **aws-keypair**.
  + Còn lại để mặc định.
  + Nhấn **Create key pair**.

![EC2](/images/2.prerequisite/EC2_5.png)

6. Cấu hình **Network settings**.
  + Chọn **Edit**.

![EC2](/images/2.prerequisite/EC2_6.png)

7. để tiếp tục.
  + **VPC - required** chọn **project-vpc**.
  + **Subnet** chọn **project-subnet-public1-us-east-1a**.
  + **Firewall (security groups)** chọn **Select existing security group**.
  + **Common security groups** chọn **ec2-rds-1**.
  + Sau đó nhấn **Launch instance**.

![EC2](/images/2.prerequisite/EC2_7.png)