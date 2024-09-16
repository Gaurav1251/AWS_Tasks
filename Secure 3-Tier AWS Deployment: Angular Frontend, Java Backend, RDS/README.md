# Secure 3-Tier AWS Deployment: Angular Frontend, Java Backend, RDS
---

![Screenshot from 2024-09-16 16-00-45](https://github.com/user-attachments/assets/3dd35297-4c06-4bfc-88a1-fbd73d9717cd)


This guide provides a comprehensive walkthrough for deploying a secure 3-tier application on AWS, featuring an Angular frontend, a Java-based backend, and a MariaDB database hosted on AWS RDS. The deployment ensures secure communication, scalable architecture, and efficient traffic management using AWS services.
Table of Contents

---
    Overview
    Key Components
    Architecture Diagram
    Steps to Configure the Deployment
        Step 1: Create a VPC with Subnets and NAT
        Step 2: Launch EC2 Instances
        Step 3: Configure Security Groups
        Step 4: Configure Bastion Server
        Step 5: Connect to Private Servers
        Step 6: Clone GitHub Repository
        Step 7: Set Up MariaDB on Database Server
        Step 8: Set Up RDS for Production
        Step 9: Connect Backend to RDS
        Step 10: Set Up Backend Server
        Step 11: Update Backend Configuration
        Step 12: Set Up Frontend Server
        Step 13: Configure Network Load Balancers
        Step 14: Configure Frontend Access
        Step 15: Handle CORS Issues
        Step 16: Build Frontend
        Step 17: Deploy Frontend with NGINX
        Step 18: Deploy Backend Application
        Step 19: Configure AWS CLI on Frontend
        Step 20: Create and Configure S3 Bucket
        Step 21: Set Up CloudFront Distribution
        Step 22: Set Up Route 53 for Domain
        Step 23: Add CNAME to CloudFront
        Step 24: Secure Your Domain
        Step 25: Automate Database Backups
        Step 26: Create S3 Bucket for Database Backup
        Step 27: Remove NAT Gateway and Use VPC Endpoint
        Step 28: Create Backup Script and Use Crontab
        Step 29: Monitor Application with CloudWatch
    Conclusion
    License

**Overview**<br>

This guide covers the deployment of a secure and scalable 3-tier application on AWS using the following components:

    Angular Frontend: Deployed on an EC2 instance in a public subnet with NGINX.
    Java Backend: Deployed on an EC2 instance in a private subnet, connected via a Network Load Balancer (NLB).
    MariaDB Database: Hosted on AWS RDS, with connections managed through security group rules and VPC configurations.
---
**Key Components**

    VPC: A Virtual Private Cloud that hosts all resources in a secure, isolated environment.
    EC2 Instances: Virtual servers for hosting the frontend, backend, and database applications.
    RDS (MariaDB): Managed database service for the backend.
    Security Groups: Firewall rules for controlling inbound and outbound traffic.
    NAT Gateway: Allows private instances to connect to the internet while remaining secure.
    S3: For storage of static assets and database backups.
    CloudFront: CDN for serving static content securely.
    Route 53: Domain management and DNS routing.
    ACM: For issuing SSL certificates to secure the website.

**Architecture Diagram**

For a visual representation of the architecture, refer to the diagram available here https://drive.google.com/file/d/1w9YR_SkHr1GC3JmxukGFPqMwSeWVHbR8/view <br>

---
**Steps to Configure the Deployment**<br>

Step 1: Create a VPC with Subnets and NAT

    Set up a VPC with one public subnet and two private subnets.
    Add a NAT Gateway to allow private subnets to access the internet.

Step 2: Launch EC2 Instances

    Launch the frontend, backend, and database servers within the respective subnets.
    Ensure public IP assignment for the frontend server and disable public IP for backend and database servers.

Step 3: Configure Security Groups

    Whitelist necessary ports (22, 443, 80, 8080, 3306) for communication between servers and clients.

Step 4: Configure Bastion Server

    Use the frontend server as a bastion (jump) server for secure access to private instances.

Step 5: Connect to Private Servers

    Transfer the SSH private key to the frontend server and use it to connect to the backend and database servers securely.

Step 6: Clone GitHub Repository

    Clone the application code from GitHub to all three servers using git clone https://github.com/rajatpzade/angular-java.git.

Step 7: Set Up MariaDB on Database Server

    Install MariaDB on the database server, start and enable the service.

Step 8: Set Up RDS for Production

    Create a production database named angular-java on RDS, choosing MariaDB as the engine.

Step 9: Connect Backend to RDS

    Configure the backend server to connect to the RDS instance by updating the application configuration.

Step 10: Set Up Backend Server

    Install required software (OpenJDK, Maven) on the backend server and build the backend application.

Step 11: Update Backend Configuration

    Modify application.properties with the RDS endpoint, username, and password details.

Step 12: Set Up Frontend Server

    Install Node.js, npm, and Angular CLI on the frontend server, and build the Angular application.

Step 13: Configure Network Load Balancers

    Set up NLBs for both the backend and frontend servers to handle traffic efficiently.

Step 14: Configure Frontend Access

    Deploy the frontend using NGINX and configure it to serve static files.

Step 15: Handle CORS Issues

    Update backend configuration to handle CORS by specifying allowed origins.

Step 16: Build Frontend

    Build the Angular frontend using ng build --configuration production.

Step 17: Deploy Frontend with NGINX

    Deploy the built frontend files to the NGINX server on the frontend EC2 instance.

Step 18: Deploy Backend Application

    Run the backend application using java -jar command.

Step 19: Configure AWS CLI on Frontend

    Install AWS CLI on the frontend server and attach necessary IAM roles for S3 access.

Step 20: Create and Configure S3 Bucket

    Create an S3 bucket for storing static files and configure permissions for public access.

Step 21: Set Up CloudFront Distribution

    Set up a CloudFront distribution with the S3 bucket as the origin and apply SSL certificates.

Step 22: Set Up Route 53 for Domain

    Create a Hosted Zone in Route 53 and configure the domain to use AWS name servers.

Step 23: Add CNAME to CloudFront

    Update CloudFront configuration to include a CNAME record for your domain.

Step 24: Secure Your Domain

    Request an SSL certificate from ACM and attach it to the CloudFront distribution.

Step 25: Automate Database Backups

    Set up automated backups to S3 using AWS CLI on the database server.

Step 26: Create S3 Bucket for Database Backup

    Create a dedicated S3 bucket with versioning enabled for database backups.

Step 27: Remove NAT Gateway and Use VPC Endpoint

    Replace NAT Gateway with an S3 VPC Endpoint to securely access S3 from private subnets.

Step 28: Create Backup Script and Use Crontab

    Automate database backups using a shell script and crontab.

Step 29: Monitor Application with CloudWatch

    Set up CloudWatch dashboards to monitor the performance and health of the application.
---
**Conclusion**

By following these steps, you will have successfully deployed a secure and scalable 3-tier application on AWS, leveraging key services like EC2, RDS, S3, and CloudFront. This setup ensures robust security, efficient traffic management, and optimal performance.
<br>

---
**License**

This project is licensed under the MIT License - see the LICENSE file for details.
