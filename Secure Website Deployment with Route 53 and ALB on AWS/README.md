**Secure Website Deployment with Route 53 and ALB on AWS**
---

This guide demonstrates how to set up a secure and scalable website using Amazon Web Services (AWS). The process includes creating an EC2 instance, configuring a web server, purchasing a domain from a third-party provider, and securing the website with SSL/TLS certificates issued by AWS Certificate Manager (ACM). Traffic management is handled efficiently using an Application Load Balancer (ALB).
Table of Contents

    
    Key Components
    Task Overview
    Steps to Configure the Website
        Step 1: Set Up EC2 Instance
        Step 2: Deploy Website
        Step 3: Configure Security
        Step 4: Set Up Domain and DNS
        Step 5: Secure the Website
        Step 6: Final Check
    Conclusion
    License
---
**Task Overview**

This task guides you through setting up a secure website on AWS. You will deploy an EC2 instance, configure a web server, purchase and link a domain, and secure your site with SSL/TLS using ACM, with traffic managed by an Application Load Balancer.
Key Components

    EC2 Instance: A virtual server in AWS used to run the web server.
    Apache HTTP Server (httpd): Web server software for hosting the website.
    Route 53: AWS’s scalable DNS web service for routing traffic to your application.
    SSL/TLS Certificate: Issued by ACM to secure your website.
    Application Load Balancer: Distributes incoming traffic across multiple targets.
    Third-Party Domain: A domain purchased from a provider like Hostinger and configured in AWS.
---
**Steps to Configure the Website**
Step 1: Set Up EC2 Instance

    Create an EC2 Instance:

    bash

ssh -i private_rsa_key ec2-user@public_ip

Install Apache HTTP Server (httpd):

bash

    sudo -i
    yum install httpd -y

Step 2: Deploy Website

    Install and Host a Free CSS Template:

    bash

    sudo wget url_of_webpage_codes

    Copy the files to the home directory of httpd at /var/www/html/.

Step 3: Configure Security

    Whitelist Ports 80 and 443 in the EC2 instance's security group.

Step 4: Set Up Domain and DNS

    Purchase a Domain from a third-party provider (e.g., Hostinger).
    Create a Hosted Zone in Route 53 to bind the domain with the public IP.
    Update Name Server (NS) Records with the domain provider.
    Create an A Record in Route 53 to bind the public IP with the domain.

Step 5: Secure the Website

    Request an SSL Certificate from ACM.
    Create a CNAME Record in Route 53 to verify domain ownership.
    Create an Application Load Balancer (ALB) and attach the SSL certificate.
    Update the A Record to point the domain to the ALB's DNS.

Step 6: Final Check

    Test the Domain to ensure it is accessible and secure.
---
**Conclusion:**

By following these steps, you will have successfully set up and secured a website using AWS services, ensuring efficient traffic management and secure communications.<br>

**License**

This project is licensed under the MIT License - see the LICENSE file for details.
