---
title : "Tạo cơ sở dữ liệu RDS"
date: "2025-06-14"
weight : 6
chapter : false
pre : " <b> 2.3 </b> "
---

### Tạo Subnet group ###

1. Truy cập [giao diện quản trị dịch vụ RDS](https://console.aws.amazon.com/rds/home)
   + Chọn **Subnet groups**.
   + Chọn **Create DB Subnet group**.

![RDS](/images/2.prerequisite/RDS_Subnet_1.png)

2. Tại trang **Create DB Subnet group**.

    + Tại ô **Name** điền **database-subnet-1**.
    + Tại ô **Description** điền **subnet for database 1**.
    + Ở phần **VPC** chọn **project-vpc**.
    + Ở phần **Availability Zones** chọn **us-east-1a** và **us-east-1b**.

![RDS](/images/2.prerequisite/RDS_Subnet_2.png)

3. Tại phần **Subnets**. 

    + Chọn **project-subnet-private2-us-east-1b** và **project-subnet-private1-us-east-1a**.

![RDS](/images/2.prerequisite/RDS_Subnet_3.png)

4. Nhấn **Create**.

![RDS](/images/2.prerequisite/RDS_Subnet_4.png)


### Tạo RDS ###

1. Truy cập [giao diện quản trị dịch vụ RDS](https://console.aws.amazon.com/rds/home)

    + Chọn **Databases**.
    + Chọn **Create database**.

![RDS](/images/2.prerequisite/RDS_1.png)

2. Tại trang **Create database**.

    + Chọn **Standard create**.
    + Ở phần **Engine options** chọn **MySQL**.
  
![RDS](/images/2.prerequisite/RDS_2.png)

3. Kéo xuống dưới.

    + Ở phần **Templates** chọn **Dev/test**.
    + Ở phần **Availability and durability** chọn **Single-AZ DB instance deployment (1 instance)**.
 
![RDS](/images/2.prerequisite/RDS_3.png)

4. Kéo xuống phần **Setting**

    + Ở phần **DB instance identifier** đặt tên là **database-1** (tùy mọi người đặt).
    + Trong phần **Credentials Settings** chọn **Self managed**.
    + Ở ô **Master password** nhập mật đủ mạnh.
    + Sau đó nhập lại mật khẩu ở ô **Confirm master password**.

![RDS](/images/2.prerequisite/RDS_4.png)

5. Kéo xuống phần **Instance configuration**.

    + Chọn **Burstable classes (includes t classes)**.
    + Chọn **db.t3.micro**.

![RDS](/images/2.prerequisite/RDS_5.png)

6. Kéo xuống phần **Connectivity**.

    + Chọn **Connect to an EC2 compute resource**.
    + Ở phần **EC2 instance** chọn **Order-API-EC2**.

![RDS](/images/2.prerequisite/RDS_6.png)

7. Tiếp tục xuống phần **DB subnet group** để tiếp tục.

    + Chọn **Choose existing**
    + Ở phần **Existing DB subnet groups** chọn **database-subnet-1**.
    + Ở phần **Additional VPC security group** chọn **Private-DB-Sg**.

![RDS](/images/2.prerequisite/RDS_7.png)

8. Ở phần **Database authentication** ta để mặc định.

![RDS](/images/2.prerequisite/RDS_8.png)

9. Tại phần **Log exports**.

    + Ta chọn **Error log** và **Slow query log**.
    + Sau đó chọn **Create database**.

![RDS](/images/2.prerequisite/RDS_9.png)

10. Đợi một lúc để tạo RDS.

![RDS](/images/2.prerequisite/RDS_10.png)


