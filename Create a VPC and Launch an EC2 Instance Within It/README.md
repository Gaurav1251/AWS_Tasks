**Create a VPC and Launch an EC2 Instance Within It**
---

This guide provides a detailed step-by-step process for creating a Virtual Private Cloud (VPC) and launching an EC2 instance within it in AWS. By following this guide, you will establish a secure and isolated network environment, enabling controlled access to your cloud resources.
Table of Contents

    Task Overview
    Key Components
    Steps to Create a VPC and EC2 Instance
        Step 1: Create a VPC
        Step 2: Create a Subnet
        Step 3: Create and Attach an Internet Gateway
        Step 4: Create and Associate a Route Table
        Step 5: Launch an EC2 Instance
        Step 6: Configure Network Settings for EC2
        Step 7: Connect to Your EC2 Instance
    Conclusion
    License
---
**Task Overview **<br>

This task involves creating a Virtual Private Cloud (VPC) and launching an EC2 instance within it. A VPC allows you to control your network environment, providing isolation and security for your cloud resources.
Key Components

    VPC (Virtual Private Cloud): A virtual network dedicated to your AWS account, offering control over IP address ranges, subnets, and routing tables.
    Subnet: A segment of a VPC's IP address range where you can place AWS resources like EC2 instances.
    Internet Gateway (IGW): A gateway that enables communication between your VPC and the internet.
    Route Table: A set of rules that determine where network traffic is directed within your VPC.
    EC2 Instance: A virtual server used to run applications in the cloud.

**Steps to Create a VPC and EC2 Instance**<br>
Step 1: Create a VPC

    What is a VPC?
    A Virtual Private Cloud (VPC) is a virtual network dedicated to your AWS account, providing isolation and security within a public cloud environment. It allows you to control your network configuration, such as IP address ranges and subnets.

    Create the VPC:
        Go to the VPC Dashboard in AWS Management Console.
        Create a new VPC with the desired CIDR block (e.g., 10.0.0.0/16).

Step 2: Create a Subnet

    What is a Subnet?
    A subnet is a segmented piece of a larger network that allows for more efficient management and organization of IP addresses, helping to isolate traffic and enhance security within a VPC.

    Create the Subnet:
        In the VPC Dashboard, create a subnet within your VPC, specifying an appropriate CIDR block (e.g., 10.0.1.0/24).

Step 3: Create and Attach an Internet Gateway

    What is an Internet Gateway?
    An Internet Gateway (IGW) enables communication between instances in your VPC and the internet.

    Create the Internet Gateway:
        Create an Internet Gateway in the VPC Dashboard.
        Attach it to your VPC.

Step 4: Create and Associate a Route Table

    What is a Route Table?
    A route table is a set of rules that directs how traffic should be routed within a network.

    Create and Associate the Route Table:
        Create a route table in the VPC Dashboard.
        Edit the routes to allow traffic to the Internet Gateway.
        Associate the route table with your subnet.

Step 5: Launch an EC2 Instance

    Launch the EC2 Instance:
        Navigate to the EC2 Dashboard and launch a new EC2 instance.

Step 6: Configure Network Settings for EC2

    Configure the VPC and Subnet:
        In the network settings, select the VPC and subnet you created.
        Enable a public IP for SSH access.

Step 7: Connect to Your EC2 Instance

    Connect Using SSH:
        Copy the public IP of the EC2 instance.
        Use the following command to connect:

        bash

        ssh -i private_key.pem user@public_ip

        Verify internet connectivity by pinging 8.8.8.8.

**Conclusion**<br>

Creating a VPC and launching an EC2 instance within it provides a secure and isolated network environment in the cloud. This setup enables controlled access to resources and the internet, ensuring efficient management and enhanced security for your cloud infrastructure.
<br>

**License**

This guide is licensed under the MIT License. See the LICENSE file for details.
