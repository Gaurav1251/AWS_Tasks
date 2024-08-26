**Creation of EC2 Instance and Connecting Over SSH**
---
This guide provides a step-by-step process for creating an Amazon EC2 instance and connecting to it securely using SSH. An EC2 instance is a virtual server in Amazon's Elastic Compute Cloud (EC2) that allows you to run applications in the cloud.

**Table of Contents**

    Task Overview
    Key Components
    Steps to Create an EC2 Instance
        Step 1: Launch a New EC2 Instance
        Step 2: Configure Key Pair and Security Group
        Step 3: Connect to Your EC2 Instance
    Conclusion
    License
---
**Task Overview**<br>
This task guides you through setting up an EC2 instance on AWS. You will launch an instance, configure security settings, and connect to it using SSH, enabling you to manage applications in the AWS cloud effectively.
**Key Components**

    EC2 Instance: A virtual server that runs applications in the cloud.
    Key Pair: A pair of cryptographic keys used for secure SSH access.
    Security Group: A virtual firewall that controls inbound and outbound traffic to your instance.
    SSH Client: A software application used to connect to the EC2 instance securely.


**Steps to Create an EC2 Instance**<br>
Step 1: Launch a New EC2 Instance

    Log in to your AWS Management Console.
    Navigate to the EC2 Dashboard.
    Click on "Launch Instance."
    Choose an Amazon Machine Image (AMI) that suits your needs.
    Select an instance type and configure instance details as required.

Step 2: Configure Key Pair and Security Group

    Key Pair:
        A key pair consists of a public key (stored by AWS) and a private key (retained by you for SSH access).
        To create a new key pair, select "Create a new key pair" and download the .pem file.
        Alternatively, you can use an existing key pair.
    Security Group:
        This acts as a virtual firewall for your instance.
        You can either select an existing security group or create a new one.
        Ensure that port 22 is open to allow SSH access.

Step 3: Connect to Your EC2 Instance

    After the instance is launched, copy the public IP address of the instance.
    Set the correct permissions for your private key file:


**chmod 600 private_key_pair.pem**

    Use the following command to connect to your EC2 instance:


**ssh -i private_key_pair.pem user_name@public_ip**

    Replace user_name with the appropriate username (e.g., ec2-user, ubuntu, etc.) and public_ip with the copied public IP address.
---







**Conclusion:**
Successfully creating and connecting to an EC2 instance via SSH is a fundamental task for managing applications in the AWS cloud. This process enables effective cloud infrastructure management and deployment of applications.

<br>

**License**
This project is licensed under the MIT License - see the LICENSE file for details.
