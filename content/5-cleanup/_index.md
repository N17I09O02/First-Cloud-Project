+++
title = "Resource Cleanup"
date = "2025-06-14"
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

We will proceed with the following steps to delete the resources we created in this exercise.

1. Access the [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)  
  + Click **Instances**.  
  + Select both instances: **Public Linux Instance** and **Private Windows Instance**.  
  + Click **Instance state**.  
  + Click **Terminate instance**, then click **Terminate** to confirm.

![Clean](/images/Delete_EC2_1.png)

2. Access the [IAM service management console](https://console.aws.amazon.com/iamv2/home#/home)  
  + Click **Roles**.  
  + In the search box, enter **Lambda_S3_Notify_Role**.  
  + Click on **Lambda_S3_Notify_Role**.  
  + Click **Delete**, then enter the role name **Lambda_S3_Notify_Role** and click **Delete** to delete the role.  
  + Do the same for **LambdaStopEC2Role**.

![Clean](/images/Delete_S3_1.png)

4. Access the [S3 service management console](https://s3.console.aws.amazon.com/s3/home)  
  + Click the S3 bucket we created for the exercise.  
  + Click **Empty**.  
  + Enter **permanently delete**, then click **Empty** to proceed with deleting the objects in the bucket.  
  + Click **Exit**.  
  + To ensure a complete cleanup, you can refer to https://000057.awsstudygroup.com/11-cleanup/  
  ![Clean](/images/Delete_S3_2.png)

5. Access the [RDS service management console](https://s3.console.aws.amazon.com/s3/home)  

  + Select **database-1**.  
  + Click **Actions**.  
  + Click **Delete**.

  ![Clean](/images/Delete_RDS_1.png)

  + Uncheck **Create final snapshot** and **Retain automated backups**.  
  + Check **I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available**.  
  + Enter **delete me** into the **To confirm deletion, type delete me into the field**.

  ![Clean](/images/Delete_RDS_2.png)

6. Access the [VPC service management console](https://s3.console.aws.amazon.com/vpcconsole/home)  
  + You can refer to the cleanup steps in this lab: https://000003.awsstudygroup.com/6-cleanup/  
  + Delete Subnet  
  ![Clean](/images/Delete_VPC_1.png)  
  ![Clean](/images/Delete_VPC_1.1.png)

  + Delete SecurityGroup  
  ![Clean](/images/Delete_VPC_2.png)  
  ![Clean](/images/Delete_VPC_2.2.png)

  + Delete router  
  ![Clean](/images/Delete_VPC_3.png)

  + Delete Your VPC  
  ![Clean](/images/Delete_VPC_4.png)  
  ![Clean](/images/Delete_VPC_4.1.png)

7. Access the [SNS service management console](https://s3.console.aws.amazon.com/sns/v3/home)

  ![Clean](/images/Delete_SNS_1.png)

  ![Clean](/images/Delete_SNS_2.png)

8. Access the [Lambda service management console](https://s3.console.aws.amazon.com/lambda/home)

  ![Clean](/images/Delete_Lambda_1.png)

  ![Clean](/images/Delete_Lambda_2.png)

9. Access the [CloudWatch service management console](https://s3.console.aws.amazon.com/cloudwatch/home)

  ![Clean](/images/Delete_CW_1.png)

  ![Clean](/images/Delete_CW_2.png)
