---
title : "Đưa csdl từ local lên RDS"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---


1. Mở terminal hoặc powershell trên máy của bạn.
  + chạy lệnh 
  ```
    scp -i your-key.pem C:/duong-dan/Tên file .sql ec2-user@'EC2_PUBLIC_IP':~/
  ```
  ![SG](/images/3.connect/EC2_connect/RDS_CN_1.png)

2. Sau khi chạy xong thì mở EC2 và chạy thử
  + **ls -lh Tên file .sql**
  ![SG](/images/3.connect/EC2_connect/RDS_CN_2.png)

3. Import vào RDS
  + Truy cập vào RDS để lấy EndPoint
  ![SG](/images/3.connect/EC2_connect/RDS_CN_3.png)

4. Đăng nhập vào RDS
   + Lệnh đăng nhập RDS **mysql -h 'End-Point-RDS' -P 3306 -u admin -p**
   + Bạn sẽ được yêu cầu nhập mật khẩu để vào RDS, hãy nhập mật khẩu lúc bạn tạo RDS là được.

  ![SG](/images/3.connect/EC2_connect/RDS_CN_4.png)
  
5. Tạo database
   + Lệnh tạo database **CREATE DATABASE QuanLyDonHangDB;**
   + Lệnh thoát **EXIT;**
  ![SG](/images/3.connect/EC2_connect/RDS_CN_6.png)

6. Sau đó chạy lệnh sau để import dự liệu vào
   + mysql -h <rds-endpoint> -P 3306 -u admin -p QuanLyDonHangDB < QuanLyDonHangDB.sql
  ![SG](/images/3.connect/EC2_connect/RDS_CN_5.png)

7. Kết nối csdl với web

   ```
    "ConnectionStrings": {
      "DefaultConnection": "Server=<Địa chỉ end point của RDS>;Port=3306;Database=<Tên database>;User=admin;Password=<Mật khẩu database>;"
    },
   ```
   ![SG](/images/3.connect/EC2_connect/EC2_CN_RDS.png)
