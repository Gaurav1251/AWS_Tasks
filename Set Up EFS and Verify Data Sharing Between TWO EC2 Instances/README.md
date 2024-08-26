**Set Up EFS and Verify Data Sharing Between Two EC2 Instances**
---

This guide provides a comprehensive step-by-step process to set up an Elastic File System (EFS) in AWS and verify data sharing between two EC2 instances. The task demonstrates the capability of creating a scalable, shared storage solution that allows seamless data sharing across multiple EC2 instances.
Table of Contents

    Task Overview
    Key Components
    Steps to Set Up EFS and EC2 Instances
        Step 1: Create an EFS in AWS
        Step 2: Launch and Configure the First EC2 Instance
        Step 3: Mount the EFS on the First EC2 Instance
        Step 4: Add Data to the EFS from the First EC2 Instance
        Step 5: Launch and Configure the Second EC2 Instance
        Step 6: Mount the EFS on the Second EC2 Instance
        Step 7: Verify Data Sharing Between EC2 Instances
    Conclusion
    License
---
**Task Overview**
This task involves creating an Elastic File System (EFS) in AWS, attaching it to one EC2 instance, adding data, and then attaching another EC2 instance to the same EFS to verify that the data added by the first instance is accessible from the second one.
Key Components

    EFS (Elastic File System): A scalable file storage service that allows multiple EC2 instances to access a common file system.
    EC2 Instance: A virtual server used to run applications and manage data in the cloud.
    NFS (Network File System): A protocol that allows for file sharing over a network.
    nfs-common Package: A package providing NFS client utilities required to mount and interact with EFS.
---
**Steps to Set Up EFS and EC2 Instances**:<br>
Step 1: Create an EFS in AWS

    Log in to the AWS Management Console.
    Create a new EFS, which will be used as shared storage between the EC2 instances.

Step 2: Launch and Configure the First EC2 Instance

    Launch a new EC2 instance in the same VPC as the EFS.
    Access the instance via SSH.

Step 3: Mount the EFS on the First EC2 Instance

    Install the nfs-common package.
    Create a mount directory and mount the EFS using the DNS name provided by AWS.

Step 4: Add Data to the EFS from the First EC2 Instance

    Navigate to the mounted directory and create some files.

Step 5: Launch and Configure the Second EC2 Instance

    Launch a second EC2 instance in the same VPC.
    Access the instance via SSH.

Step 6: Mount the EFS on the Second EC2 Instance

    Install the nfs-common package.
    Mount the EFS in the same way as on the first EC2 instance.

Step 7: Verify Data Sharing Between EC2 Instances

    Navigate to the mounted EFS on the second EC2 instance.
    Verify that the files created by the first EC2 instance are accessible.
---
**Conclusion:**

Successfully setting up an EFS and attaching it to multiple EC2 instances ensures seamless data sharing across instances. This task is essential for managing distributed applications and maintaining data consistency in a cloud environment.
<br>

**License:**

This guide is licensed under the MIT License. See the LICENSE file for details.
