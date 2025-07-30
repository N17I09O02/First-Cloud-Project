---
title : "Upload local database to RDS"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

1. Open terminal or PowerShell on your machine.  
  + Run the command:
```
  scp -i your-key.pem C:/path-to/your-file.sql ec2-user@'EC2_PUBLIC_IP':~/
```

![SG](/images/3.connect/EC2_connect/RDS_CN_1.png)

2. After running the command, open EC2 and verify:
+ **ls -lh your-file.sql**
![SG](/images/3.connect/EC2_connect/RDS_CN_2.png)

3. Import into RDS:  
+ Go to the RDS console to get the **Endpoint**
![SG](/images/3.connect/EC2_connect/RDS_CN_3.png)

4. Log in to RDS:  
 + Command to log in to RDS: **mysql -h 'RDS-End-Point' -P 3306 -u admin -p**  
 + You will be prompted to enter the password — just enter the one you used when creating RDS.

![SG](/images/3.connect/EC2_connect/RDS_CN_4.png)

5. Create a database:  
 + Command to create database: **CREATE DATABASE QuanLyDonHangDB;**  
 + Exit command: **EXIT;**
![SG](/images/3.connect/EC2_connect/RDS_CN_6.png)

6. Then run the following command to import the data:  
 + `mysql -h <rds-endpoint> -P 3306 -u admin -p QuanLyDonHangDB < QuanLyDonHangDB.sql`
![SG](/images/3.connect/EC2_connect/RDS_CN_5.png)

7. Connect the database to the web project:

```
"ConnectionStrings": {
  "DefaultConnection": "Server=<RDS endpoint address>;Port=3306;Database=<Database name>;User=admin;Password=<Database password>;"
},
```
![SG](/images/3.connect/EC2_connect/EC2_CN_RDS.png)
