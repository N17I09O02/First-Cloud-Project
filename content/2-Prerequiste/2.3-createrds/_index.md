---
title : "Create RDS Database"
date: "2025-06-14"
weight : 6
chapter : false
pre : " <b> 2.3 </b> "
---

### Create Subnet Group ###

1. Go to the [RDS service management console](https://console.aws.amazon.com/rds/home)  
   + Select **Subnet groups**.  
   + Click **Create DB Subnet group**.

![RDS](/images/2.prerequisite/RDS_Subnet_1.png)

2. On the **Create DB Subnet group** page:  
    + In the **Name** field, enter **database-subnet-1**.  
    + In the **Description** field, enter **subnet for database 1**.  
    + In the **VPC** section, select **project-vpc**.  
    + In the **Availability Zones** section, select **us-east-1a** and **us-east-1b**.

![RDS](/images/2.prerequisite/RDS_Subnet_2.png)

3. In the **Subnets** section:  
    + Select **project-subnet-private2-us-east-1b** and **project-subnet-private1-us-east-1a**.

![RDS](/images/2.prerequisite/RDS_Subnet_3.png)

4. Click **Create**.

![RDS](/images/2.prerequisite/RDS_Subnet_4.png)


### Create RDS ###

1. Go to the [RDS service management console](https://console.aws.amazon.com/rds/home)  
    + Select **Databases**.  
    + Click **Create database**.

![RDS](/images/2.prerequisite/RDS_1.png)

2. On the **Create database** page:  
    + Select **Standard create**.  
    + In the **Engine options** section, choose **MySQL**.

![RDS](/images/2.prerequisite/RDS_2.png)

3. Scroll down:  
    + In the **Templates** section, select **Dev/test**.  
    + In the **Availability and durability** section, select **Single-AZ DB instance deployment (1 instance)**.

![RDS](/images/2.prerequisite/RDS_3.png)

4. Scroll to the **Settings** section:  
    + In the **DB instance identifier** field, enter **database-1** (you can change this).  
    + In the **Credentials Settings** section, select **Self managed**.  
    + Enter a strong password in the **Master password** field.  
    + Re-enter the password in the **Confirm master password** field.

![RDS](/images/2.prerequisite/RDS_4.png)

5. Scroll to the **Instance configuration** section:  
    + Choose **Burstable classes (includes t classes)**.  
    + Select **db.t3.micro**.

![RDS](/images/2.prerequisite/RDS_5.png)

6. Scroll to the **Connectivity** section:  
    + Select **Connect to an EC2 compute resource**.  
    + In the **EC2 instance** field, choose **Order-API-EC2**.

![RDS](/images/2.prerequisite/RDS_6.png)

7. Continue to the **DB subnet group** section:  
    + Choose **Choose existing**.  
    + In the **Existing DB subnet groups** field, select **database-subnet-1**.  
    + In the **Additional VPC security group** field, select **Private-DB-Sg**.

![RDS](/images/2.prerequisite/RDS_7.png)

8. In the **Database authentication** section, leave it as default.

![RDS](/images/2.prerequisite/RDS_8.png)

9. In the **Log exports** section:  
    + Select **Error log** and **Slow query log**.  
    + Then click **Create database**.

![RDS](/images/2.prerequisite/RDS_9.png)

10. Wait a moment for the RDS to be created.

![RDS](/images/2.prerequisite/RDS_10.png)
