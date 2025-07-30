---
title : "Create Public Linux EC2"
date: "2025-06-14"
weight : 5
chapter : false
pre : " <b> 2.1.3 </b> "
---

1. Go to the [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)  
  + Click **Instances**.  
  + Click **Launch instances**.  

![EC2](/images/2.prerequisite/EC2_1.png)

2. On the **Launch an instance** page:  
  + In the **Name and tags** section, enter **OrderAPI-EC2**.  
  + In the **Application and OS Images (Amazon Machine Image)** section, select **Amazon Linux**.  

![EC2](/images/2.prerequisite/EC2_2.png)

3. In the **Instance type** section:  
 + Select **t2.micro**.  

![EC2](/images/2.prerequisite/EC2_3.png)

4. Create a KeyPair.  
  + In the **Key pair name - required** section, select **Create new key pair**.  

![EC2](/images/2.prerequisite/EC2_4.png)

5. On the **Create key pair** interface:  
  + Enter **aws-keypair** in **Key pair name**.  
  + Leave the rest as default.  
  + Click **Create key pair**.  

![EC2](/images/2.prerequisite/EC2_5.png)

6. Configure **Network settings**.  
  + Click **Edit**.  

![EC2](/images/2.prerequisite/EC2_6.png)

7. To proceed:  
  + For **VPC - required**, select **project-vpc**.  
  + For **Subnet**, select **project-subnet-public1-us-east-1a**.  
  + For **Firewall (security groups)**, select **Select existing security group**.  
  + In **Common security groups**, select **ec2-rds-1**.  
  + Then click **Launch instance**.  

![EC2](/images/2.prerequisite/EC2_7.png)
