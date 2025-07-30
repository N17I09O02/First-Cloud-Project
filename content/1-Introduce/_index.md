---
title : "Introduction"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

The system is deployed on the AWS cloud platform to ensure performance, security, and scalability for the web application.

The architecture uses core AWS services such as EC2, RDS, S3, IAM, VPC, CloudWatch, Lambda, and SNS, aiming to deploy a complete system from processing to monitoring, access control, and automated alerts.

Main components of the system:
 - EC2: Used to run the main project (web application or backend API) with flexible customization of server configuration and scalability when needed.

 - RDS: Provides centralized database management (e.g., MySQL, PostgreSQL) and is placed in a separate VPC to enhance security and prevent unauthorized access from the internet.

 - S3: Used to store images, static documents, or media content from the system with unlimited scalability and low cost.

 - IAM: Manages user access permissions (Admin, Dev...) according to the principle of least privilege, ensuring users have only the necessary permissions in the system.

 - CloudWatch: Monitors and observes system performance, including EC2, RDS, and Lambda resources. Logs and alerts when abnormalities occur, such as high CPU usage or connection errors.

 - Lambda: Executes automated functions – for example, sending notifications when EC2 CPU exceeds thresholds or when specific events occur in the system.

 - SNS: Works with Lambda to send alert emails to administrators when incidents occur (such as CPU overload or application errors).

 - VPC: Configures a Virtual Private Cloud to ensure the system operates in an isolated, secure environment with better network control.

Advantages of the architecture:
 - Automated and intelligent monitoring and alerting helps detect issues early.

 - Clear permission separation between Dev and Admin via IAM.

 - High security by not exposing RDS to direct internet access.

 - Flexible and low-cost storage via S3.

 - Easily scalable and efficiently managed through AWS’s built-in services.

With this architecture, the system not only ensures high availability but also saves operational time and management costs, making it well-suited for real-world projects in modern enterprise environments.
