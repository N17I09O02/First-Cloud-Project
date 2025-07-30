---
title : "Create Security Groups"
date: "2025-06-14"
weight : 4
chapter : false
pre : " <b> 2.1.2 </b> "
---

#### Create Security Groups

In this step, we will create the security groups used for our instances. As you can see, these security groups will not need to open traditional ports for **SSH** like port **22** or **Remote Desktop** via port **3389**.

#### Create a security group for the Linux instance in the public subnet

1. Access the [VPC service management console](https://console.aws.amazon.com/vpc)  
  + Select **Security Group**.  
  + Click **Create security group**.

![SG](/images/2.prerequisite/VPC_Security_1.png)

2. In the **Security group name** field, enter **PublicSGEC2**.  
  + In the **Description** field, enter **Public security group**.  
  + In the **VPC** field, select **project-vpc**, which we created in step 2.1.1.  
  + In the **Inbound rules** section, click **Add rule**.  
  + Set Type to **SSH**, and Source to **Anywhere**.  
  + Similarly, add two more rules as follows:  
  + Type: **HTTP**, Source: **Anywhere**  
  + Type: **HTTPS**, Source: **Anywhere**  

![SG](/images/2.prerequisite/VPC_Security_2.png)

3. Leave **Outbound rules** as default, scroll down.

![SG](/images/2.prerequisite/VPC_Security_3.png)

  + Click **Create security group**.

<!-- {{%notice tip%}}
As you can see, the security group created for the Linux public instance does not need to open traditional SSH ports such as **22**.
{{%/notice%}} -->

4. Similarly, create another security group.  
  + Name it **Private-DB-SG**  
  + In the **VPC** field, select **project-vpc**  
  + In the **Inbound rules** section, click **Add rule**  
  + Type: **MYSQL/Aurora**, Source: **Custom**, select **PublicSGEC2** that we just created

![SG](/images/2.prerequisite/VPC_Security_4.png)

5. Click **Create security group**

![SG](/images/2.prerequisite/VPC_Security_5.png)

<!-- #### Create security group for Windows instance in the private subnet

1. After successfully creating the security group for the Linux instance in the public subnet, click on the Security Groups link to return to the list.

![SG](/images/2.prerequisite/021-createsg.png)

2. Click **Create security group**.

3. In the **Security group name** field, enter **SG Private Windows Instance**.  
  + In the **Description** field, enter **SG Private Windows Instance**.  
  + In the **VPC** field, click the **X** to reselect the **Lab VPC** you created for this lab.

![SG](/images/2.prerequisite/022-createsg.png)

4. Scroll down.  
  + Add **Outbound rule** to allow TCP 443 to 10.10.0.0/16 (CIDR of the **Lab VPC** we created)  
  + Click **Create security group**

![SG](/images/2.prerequisite/023-createsg.png)

{{%notice tip%}}
For instances in the private subnet, we will connect to the **Session Manager** endpoint through an encrypted TLS connection, so we need to allow outbound connection from our instance to the VPC CIDR through port 443.
{{%/notice%}}


#### Create security group for VPC Endpoint

1. In this step, we will create a security group for the **Session Manager** VPC Endpoint.  
2. After successfully creating the security group for the Windows instance in the private subnet, click the Security Groups link to return to the list.  
3. Click **Create security group**.  
4. In the **Security group name** field, enter **SG VPC Endpoint**.  
  + In the **Description** field, enter **SG VPC Endpoint**.  
  + In the **VPC** field, click the **X** to reselect the **Lab VPC** you created for this lab.

![SG](/images/2.prerequisite/024-createsg.png)

5. Scroll down.  
  + Remove **Outbound rule**.

![SG](/images/2.prerequisite/025-createsg.png)

6. Add **Inbound rule** to allow TCP 443 from 10.10.0.0/16 (CIDR of the **Lab VPC** we created).  
  + Click **Create security group**.

![SG](/images/2.prerequisite/026-createsg.png)

That concludes the creation of necessary security groups for EC2 instances and the VPC Endpoint. -->
