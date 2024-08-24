
Task Overview
This task demonstrates how to set up a secure and scalable website using Amazon Web Services (AWS). The process involves creating an EC2 instance, configuring a web server, purchasing and configuring a domain from a third-party provider, and securing the website using SSL/TLS certificates issued by AWS Certificate Manager (ACM). Additionally, traffic is efficiently managed using an Application Load Balancer (ALB).

**Key Components**
* EC2 Instance: A virtual server in AWS used to run the web server.
* Apache HTTP Server (httpd): A web server software used to host the website.
* Route 53: AWS’s scalable DNS web service used to route end-user requests to internet applications.
* SSL/TLS Certificate: A certificate issued by ACM to secure the website.
* Application Load Balancer: Distributes incoming application traffic across multiple targets.
* Third-Party Domain: A domain purchased from a provider like Hostinger and configured in AWS.


**Steps to Configure the Website**
1. Set Up EC2 Instance
Create an EC2 Instance:
bash
Copy code
ssh -i private_rsa_key ec2-user@public_ip
Install Apache HTTP Server (httpd):
bash
Copy code
sudo -i
yum install httpd -y
2. Deploy Website
Install and Host a Free CSS Template:
bash
Copy code
sudo wget url_of_webpage_codes
Copy the files to the home directory of httpd at /var/www/html/.
3. Configure Security
Whitelist Port 80 and 443 in the EC2 instance's security group.
4. Set Up Domain and DNS
Purchase a Domain from a third-party provider (e.g., Hostinger).
Create a Hosted Zone in Route 53 to bind the domain with the public IP.
Update Name Server (NS) Records with the domain provider.
Create an A Record in Route 53 to bind the public IP with the domain.
5. Secure the Website
Request an SSL Certificate from ACM.
Create a CNAME Record in Route 53 to verify domain ownership.
Create an Application Load Balancer (ALB) and attach the SSL certificate.
Update the A Record to point the domain to the ALB's DNS.
6. Final Check
Test the domain to ensure it is accessible and secure.

**Conclusion:** By following these steps, you will have successfully set up and secured a website using AWS services, ensuring efficient traffic management and secure communications.

