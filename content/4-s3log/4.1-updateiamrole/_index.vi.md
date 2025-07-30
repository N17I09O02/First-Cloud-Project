---
title : "Đưa dự án lên EC2"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

Về cách kết nối EC2 bằng visua bạn có thể xem lại bài lab này https://000004.awsstudygroup.com/vi/

1. Bạn cần đưa dự án của bạn lên Github trước, bạn có thể xem qua bài viết này.
+ https://docs.github.com/en/get-started/start-your-journey/uploading-a-project-to-github

2. Cài Git và .NET SDK trên EC2 để có thể chạy dự án.
```
  sudo install git -y
  sudo dnf install dotnet -sdk-8.0 -y
```

  ![SG](/images/3.connect/EC2_connect/EC2_connect_1.png)

3. Clone dự án về EC2. 

   + **git clone https://github.com/'your-username'/'project-name'.git**
   + **cd 'project-name'**

  ![SG](/images/3.connect/EC2_connect/EC2_connect_2.png)

4. Các bước thực hiện chạy dự án trên EC2
   + Di chuyển đến thư mục dự bạn vừa clone **cd ~/GoodsManager**
   + Xem toàn bộ file có trong thư mục đó **ls -lh**
   + Thực hiện lệnh sau**dotnet publish 'file .csproj' -c Release -o ./publish**
   + Di chuyển vào **cd publish**
   + Tiếp tục xem toàn bộ file **ls -lh**
   + Bạn sẽ thấy những file như **.dll**, **appsettings.json** và các file cần thiết khác

5. Chạy lệnh **dotnet 'Tên file.dll' --urls "http://0.0.0.0:5000"**

   + Đường dẫn truy cập sẽ là **http://'IPV4 public của EC2':5000/**
   + Bạn sẽ thấy như sau

   ![SG](/images/3.connect/EC2_connect/EC2_connect_3.png)

6. Để sửa trực tiếp code
   + Chọn Open Folde 
   + Nhập đường dẫn chữa dự án VD : **/home/ec2-user/GoodsManage**

   ![SG](/images/3.connect/EC2_connect/Code3.png)

   + Chọn **Trust the authors of all files in the parent folder 'ec2-user'**
   + Chọn **Yes**

   ![SG](/images/3.connect/EC2_connect/Code_MOi0IzWJnM.png)

   + Đây là giao diện file dự án

   ![SG](/images/3.connect/EC2_connect/Code_1.png)
7. 

8. 

9. 
