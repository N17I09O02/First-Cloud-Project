---
title : "Deploy the Project to EC2"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

For how to connect to EC2 using Visual Studio Code, you can refer to this lab: https://000004.awsstudygroup.com/vi/

1. First, upload your project to GitHub. You can refer to this guide:  
+ https://docs.github.com/en/get-started/start-your-journey/uploading-a-project-to-github

2. Install Git and .NET SDK on EC2 to be able to run the project.

```
  sudo install git -y
  sudo dnf install dotnet -sdk-8.0 -y
```


  ![SG](/images/3.connect/EC2_connect/EC2_connect_1.png)

3. Clone the project to EC2.

   + **git clone https://github.com/'your-username'/'project-name'.git**  
   + **cd 'project-name'**

  ![SG](/images/3.connect/EC2_connect/EC2_connect_2.png)

4. Steps to run the project on EC2:  
   + Navigate to the cloned directory: **cd ~/GoodsManager**  
   + List all files in the directory: **ls -lh**  
   + Run the command: **dotnet publish 'file .csproj' -c Release -o ./publish**  
   + Move to the publish folder: **cd publish**  
   + List all files again: **ls -lh**  
   + You will see files like **.dll**, **appsettings.json**, and other required files.

5. Run the command:  
**dotnet 'YourFile.dll' --urls "http://0.0.0.0:5000"**

   + Access URL: **http://'Your EC2 Public IPV4':5000/**  
   + You will see the following:

   ![SG](/images/3.connect/EC2_connect/EC2_connect_3.png)

6. To edit code directly:  
   + Choose **Open Folder**  
   + Enter the project path, e.g.: **/home/ec2-user/GoodsManage**

   ![SG](/images/3.connect/EC2_connect/Code3.png)

   + Select **Trust the authors of all files in the parent folder 'ec2-user'**  
   + Click **Yes**

   ![SG](/images/3.connect/EC2_connect/Code_MOi0IzWJnM.png)

   + This is the project file interface:

   ![SG](/images/3.connect/EC2_connect/Code_1.png)
