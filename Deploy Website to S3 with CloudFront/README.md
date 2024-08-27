## **Deploy Website to S3 with CloudFront**

This guide provides instructions for deploying a website using Amazon S3 as the storage solution and CloudFront as the CDN.

---
**Table of Contents**

    Task Overview
    Steps to Deploy Website
        Step 1: Create an S3 Bucket
        Step 2: Upload Website Files
        Step 3: Configure S3 Bucket Permissions
        Step 4: Enable Static Website Hosting
        Step 5: Make Objects Public
        Step 6: Configure CloudFront
        Step 7: Access the Website via CloudFront
    Conclusion
    License
---
**Task Overview**<br>
This task involves deploying a website on Amazon S3 and distributing it globally using CloudFront.

---
**Steps to Deploy Website**<br>
Step 1: Create an S3 Bucket

    Create a new S3 bucket in AWS to store the website files.

Step 2: Upload Website Files

    Upload the index.html file (or other relevant files) to the S3 bucket.

Step 3: Configure S3 Bucket Permissions

    Uncheck Block Public Access in the Permissions tab.
    Enable ACLs and set public access permissions.

Step 4: Enable Static Website Hosting

    In the Properties tab, enable static website hosting.
    Set index.html as the default page.

Step 5: Make Objects Public

    Select the website files and make them public using the Make public using ACL option.

Step 6: Configure CloudFront

    Create a CloudFront distribution with the S3 bucket as the origin.
    Wait for the distribution to deploy.

Step 7: Access the Website via CloudFront

    Once the CloudFront distribution is deployed, access the website using the CloudFront DNS.
---
**Conclusion:**

Deploying a website on S3 with CloudFront provides a cost-effective and scalable solution for global content delivery.
<br>

**License:**

This guide is licensed under the MIT License. See the LICENSE file for more details.
