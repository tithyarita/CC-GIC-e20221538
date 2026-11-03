# Lab 1: Amazon EC2 (Hands-on)

## 1. Overview

This lab introduces Amazon Elastic Compute Cloud (Amazon EC2), an AWS service that provides virtual servers in the cloud.

The lab consists of two parts:
- **Part 1.1: Guided Walkthrough** – Launch and configure an EC2 instance and host a simple web page using Apache.
- **Part 1.2: EC2 Challenge** – Independently create and configure an EC2 instance to host a web page with a specified message.

## 2. Objectives

- Understand the basic concepts of Amazon EC2.
- Create and configure an EC2 security group.
- Create an SSH key pair.
- Launch an EC2 instance using Amazon Linux 2023.
- Connect to an EC2 instance using SSH.
- Install and configure the Apache web server.
- Host a simple HTML page on an EC2 instance.
- Access the web application through the instance's public IP address.

## 3. AWS Services and Tools Used

| Service / Tool | Purpose |
|---|---|
| Amazon EC2 | Launch and manage virtual servers. |
| Security Groups | Control inbound network traffic. |
| Key Pair | Authenticate SSH connections to EC2. |
| Amazon Linux 2023 | Operating system for the EC2 instance. |
| Apache HTTP Server | Host and serve the web page. |
| SSH | Connect remotely to the Linux instance. |

## 4. Part 1.1: Guided Walkthrough

### Step 1: Create a Security Group

Created a security group named `aws-bootstrap-security-group`.

Configured inbound rules:
- SSH – TCP port 22 – Anywhere IPv4 (`0.0.0.0/0`).
- HTTP – TCP port 80 – Anywhere IPv4 (`0.0.0.0/0`).

The security group allows SSH connections for server administration and HTTP requests for accessing the website.

### Step 2: Create a Key Pair

Created a key pair named `aws-bootstrap-key-pair`.

- Key pair type: RSA
- Private key format: `.pem`

The downloaded private key is used to authenticate and securely connect to the EC2 instance through SSH.

### Step 3: Launch an EC2 Instance

Created an EC2 instance named `aws-bootstrap-instance`.

Configuration:
- AMI: Amazon Linux 2023
- Instance type: `t2.micro`
- Storage: 8 GiB gp3
- Security group: `aws-bootstrap-security-group`
- Key pair: `aws-bootstrap-key-pair`

### Step 4: Configure User Data

Used the User Data script to automatically install and configure the Apache web server when the EC2 instance starts.

The script installs Apache, starts the service, enables it to start automatically, and creates an HTML page.

The web page displays:

`Hello World from Educative (hostname)`

### Step 5: Connect to the EC2 Instance

Connected to the EC2 instance using SSH and the downloaded private key.

After connecting, checked the server configuration and Apache web server status.

### Step 6: Test the Web Server

Copied the EC2 instance's public IPv4 address and opened it in a web browser using HTTP.

The browser displayed the Hello World message, confirming that the Apache web server was running successfully.

## 5. Part 1.2: EC2 Challenge

### Step 1: Launch an EC2 Instance

Created a new Linux EC2 instance to complete the challenge independently.

Required configuration:
- Operating system: Linux
- Instance type: `t2.micro`
- Public IPv4 address: Enabled
- Storage: 10 GiB
- Security group: Allows SSH (port 22) and HTTP (port 80).

### Step 2: Install and Configure the Web Server

Connected to the EC2 instance and installed an Apache or Nginx web server.

Configured the web server to start and serve a custom HTML page.

### Step 3: Create the Challenge Web Page

Created an HTML page containing the required message:

`Welcome to the EC2 Challenge`

### Step 4: Test the Challenge

Opened the instance's public IPv4 address in a web browser using HTTP.

Verified that the page displayed the required challenge message.

## 6. Expected Results

After completing the lab:

- Successfully launched an EC2 instance using Amazon Linux 2023.
- Configured security groups to allow SSH and HTTP traffic.
- Connected to the Linux instance remotely.
- Installed and started the Apache web server.
- Hosted a simple web page on the EC2 instance.
- Accessed the web page through its public IPv4 address.
- Completed the EC2 Challenge by displaying the required message.

## 7. Screenshots

Screenshots documenting the Guided Walkthrough and EC2 Challenge are stored in the `images` folder.

The screenshot files follow the required naming sequence, from:

- `01-security-group.png`
- `...`
- `10-challenge-browser.png`

## 8. Conclusion

In this lab, I learned how to launch and configure virtual servers using Amazon EC2.

I gained practical experience creating security groups, generating SSH key pairs, connecting to Linux instances, installing Apache, and hosting web pages.

The lab also helped me understand how cloud servers can host web applications and how security groups control network access.

Overall, this hands-on exercise provided a foundation for understanding AWS cloud computing and managing EC2 instances.

---

**Student ID:** `e20221538`  
**AWS Region:** `us-east-1`  
**Lab:** Amazon EC2 (Hands-on)