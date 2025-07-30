---
title : "Create IAM Role"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

#### Create IAM **Lab IAM**

1. Go to the [IAM service management console](https://console.aws.amazon.com/iam/home).  
  + Click **User groups**.  
  + Click **Create group**.

![VPC](/images/2.prerequisite/chrome_jPbVK8JPvO.png)

2. On the **Create User group** page:  
  + In the **User group** field, enter **DevGroup**.  
  + In the **Attach permissions policies - Optional** section:  
  + Select the following permissions: **AmazonS3FullAccess**, **AmazonRDSReadOnlyAccess**, **CloudWatchLogsReadOnlyAccess**, **AWSLambda_ReadOnlyAccess**.

![VPC](/images/2.prerequisite/chrome_V9jQ0qzqXv.png)

+ Click **Create user group**.

![VPC](/images/2.prerequisite/chrome_gHhpy3FMlM.png)


#### Similarly, create 2 more IAM Roles

1. Go to the [IAM service management console](https://console.aws.amazon.com/iam/home).  
   + Select **Roles**.  
   + Click **Create Role**.

![VPC](/images/2.prerequisite/IAM_1.png)

2. On the **Select trusted entity** page:  
   + Select **AWS service**.  
   + In the **Service or use case** section, choose **Lambda**.

![VPC](/images/2.prerequisite/IAM_2.png)

3. On the **Add permissions** page:  
   + Search for and select **AmazonEC2FullAccess**, **AmazonSNSFullAccess**, **CloudWatchFullAccess**.

![VPC](/images/2.prerequisite/IAM_3.png)

4. On the **Role details** page:  
   + In the **Role name** field, enter **LambdaStopEC2Role**.  
   + Review the information, then click **Create role**.

![VPC](/images/2.prerequisite/IAM_4.png)

5. Interface when the role is successfully created.

![VPC](/images/2.prerequisite/IAM_5.png)

6. Repeat from step 1.  
   + On the **Add permissions** page, search for and select **AWSLambdaBasicExecutionRole**, **AmazonSNSFullAccess**.  
   + On the **Role details** page, in the **Role name** field, enter **Lambda_S3_Notify_Role**.

![VPC](/images/2.prerequisite/IAM_6.png)

7. Click **Create role**.

![VPC](/images/2.prerequisite/IAM_7.png)
