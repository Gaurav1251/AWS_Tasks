**Deploy Website to EC2 with NGINX and CloudFront**
---

This guide provides instructions for deploying a website on an EC2 instance using NGINX as the web server and Amazon CloudFront as the CDN.

---
**Table of Contents**

    Task Overview
    Steps to Deploy Website
        Step 1: Create an EC2 Instance
        Step 2: SSH into EC2 Instance
        Step 3: Install NGINX
        Step 4: Deploy Website Files
        Step 5: Test the Deployment
        Step 6: Configure CloudFront
        Step 7: Access the Website via CloudFront
    Conclusion
    License

**Task Overview**<br>

This task involves deploying a website on an EC2 instance using NGINX and then configuring CloudFront to distribute the content globally.

---

**Steps to Deploy Website**<br>
Step 1: Create an EC2 Instance

    Launch an EC2 instance in AWS.
    Configure the security group to allow traffic on ports 22 (SSH) and 80 (HTTP).

Step 2: SSH into EC2 Instance

    SSH into the EC2 instance using the following command:



    ssh -i your-key.pem user@public_ip

Step 3: Install NGINX

    Install NGINX on the EC2 instance:

    sudo apt install nginx -y

Step 4: Deploy Website Files

    Download and extract a website template.
    Copy the extracted files to the NGINX home directory.
    Remove the default index.nginx-debian.html file.

Step 5: Test the Deployment

    Access the website using the EC2 instance's public IP to verify the deployment.

Step 6: Configure CloudFront

    Create a CloudFront distribution.
    Set the EC2 DNS as the origin domain.
    Wait for the distribution to deploy.

Step 7: Access the Website via CloudFront

    Once the CloudFront distribution is deployed, access the website using the CloudFront DNS.
---

**Conclusion:**


Deploying a website using EC2, NGINX, and CloudFront ensures scalable and globally distributed content delivery.

---
<br>

**License:**
This guide is licensed under the MIT License. See the LICENSE file for more details.
