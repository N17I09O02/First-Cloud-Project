---
title : "Tạo IAM Role"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

#### Tạo IAM **Lab IAM**

1. Truy cập [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iam/home).
  + Click **Users group**.
  + Click **Create group**.

![VPC](/images/2.prerequisite/chrome_jPbVK8JPvO.png)

2. Tại trang **Create User group**.
  + Tại mục **User group** điền **DevGroup**.
  + Tại mục **Attach permissions policies - Optional**.
  + Chọn các quyền **AmazonS3FullAccess**, **AmazonRDSReadOnlyAccess**, **CloudWatchLogsReadOnlyAcces**, **AWSLambda_ReadOnlyAccess**.

![VPC](/images/2.prerequisite/chrome_V9jQ0qzqXv.png)

+ Click **Create user group**.

![VPC](/images/2.prerequisite/chrome_gHhpy3FMlM.png)


#### Tương tự như trên ta tạo thêm 2 IAM Role nữa

1. Truy cập [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iam/home). 

   + Chọn **Roles**.
   + Chọn **Create Role**.

![VPC](/images/2.prerequisite/IAM_1.png)

2. Tại giao diện **Select trusted entity**. 

   + Chọn **AWS service**.
   + Ở phần **Service or user case** chọn **Lambda**.

![VPC](/images/2.prerequisite/IAM_2.png)

3. Tại giao diện **Add permissons**. 

   + Tìm và chọn **AmazonEC2FullAccess**, **AmazonSNSFullAccess**, **CloudWatchFullAccess**.

![VPC](/images/2.prerequisite/IAM_3.png)

4. Tại giao diện **Role details**.

   + Ở ô **Role name** nhập **LambdaStopEC2Role**.
   + Kiểm tra lại các thông tin sau đó nhấn **Create role**.

![VPC](/images/2.prerequisite/IAM_4.png)

5. Giao diện khi tạo thành công.

![VPC](/images/2.prerequisite/IAM_5.png)

6. Lập lại từ bước 1.

   + Tại giao diện **Add permissons** tìm và chọn **AWSLambdaBasicExecutionRole**, **AmazonSNSFullAccess**.
   + Tại giao diện **Role details** ở ô **Role name** nhập **Lambda_S3_Notify_Role**.

![VPC](/images/2.prerequisite/IAM_6.png)

7. Nhấn vào **Create role**.

![VPC](/images/2.prerequisite/IAM_7.png)


