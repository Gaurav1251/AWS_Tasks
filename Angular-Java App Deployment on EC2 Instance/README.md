**Angular-Java App Deployment on EC2 Instance**<br>
---

This guide demonstrates how to deploy an Angular-Java web application on an Amazon Web Services (AWS) EC2 instance. The process involves setting up the server, installing required software, configuring the database, and hosting the Angular frontend and Java backend.

**Table of Contents**

    Key Components
    Task Overview
    Steps to Configure the Application
        Step 1: Set Up EC2 Instance
        Step 2: Clone the Repository
        Step 3: Install Database
        Step 4: Configure the Database
        Step 5: Set Up Backend
        Step 6: Configure Frontend
        Step 7: Final Check
    Conclusion
    License
---

**Task Overview** <br>


This task guides you through setting up an Angular-Java web application on AWS. You will deploy an EC2 instance, configure the Java backend and Angular frontend, set up a MariaDB database, and make the application accessible via the public IP.

**Key Components**<br>

    EC2 Instance: A virtual server in AWS used to host the application.
    Git: Version control system to clone the source code.
    MariaDB: Open-source relational database for storing application data.
    Apache HTTP Server: Optional, for hosting the frontend.
    Angular CLI: Command-line interface for Angular development.
---

**Steps to Configure the Application**<br>
Step 1: Set Up EC2 Instance

    Create an EC2 instance.

    Connect to the instance:

    

    ssh -i private_key.pem ubuntu@public_ip

Step 2: Clone the Repository

    Clone the repository from GitHub:

    

    git clone https://github.com/rajatpzade/anguler-java.git

Step 3: Install Database

    Update the system and install MariaDB:

    

    sudo apt update
    sudo apt install mariadb-server -y
    sudo systemctl start mariadb
    sudo systemctl enable mariadb
    sudo mysql_secure_installation

Step 4: Configure the Database

    Log in to MariaDB and set up the database:

    

    sudo mysql -u root -p
    CREATE DATABASE springbackend;
    GRANT ALL PRIVILEGES ON springbackend.* TO 'root'@'localhost' IDENTIFIED BY 'your_password';
    exit

Import the database:

    

    sudo mysql -u root -p springbackend < springbackend.sql

Step 5: Set Up Backend

    Navigate to the springbackend folder and install Java and Maven:

    

    sudo apt update
    sudo apt install openjdk-8-jdk maven -y

**Build the backend application:**

    

    mvn clean package -Dmaven.test.skip=true

Step 6: Configure Frontend

    Install Node.js and Angular CLI:

    

    sudo apt install nodejs npm -y
    sudo npm install -g @angular/cli@14.2.1
  
**Edit the worker.service.ts file in src/app/services to replace localhost with the public IP of the instance.**<br>

---

**Build the Angular application:**

    

    cd angular-frontend
    npm install
    ng build

Step 7: Final Check

    Start the backend server:

    

    java -jar target/spring-backend-v1.jar &
---

**Start the Angular frontend:**

    

    sudo ng serve --host 0.0.0.0 --port=80

    Test the application by accessing the public IP in a web browser.

**Conclusion:**

By following these steps, you will have successfully deployed an Angular-Java web application on AWS EC2, configured with a backend in Java and a frontend in Angular.<br>

---

**License**

This project is licensed under the MIT License - see the LICENSE file for details.
