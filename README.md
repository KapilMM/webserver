# AWS Linux Web Hosting with External Free Domain, FTP, and SSL

## Description
This guide provides step-by-step instructions for setting up a robust web hosting environment on AWS. By following these steps, you'll be able to deploy a Linux web server, enable FTP access, connect an external domain, and secure your site with SSL/TLS encryption.

## Table of Contents
1. Features
2. Prerequisites
3. Installation
4. Usage
5. Contributing
6. License

## Features
- **Linux Web Server**: Deploy your website on an Amazon EC2 instance with a Linux operating system.
- **FTP Access**: Securely transfer files using vsftpd.
- **External Domain**: Link your own domain to the AWS instance.
- **SSL/TLS Encryption**: Protect your site with a free SSL certificate.

## Prerequisites
Before you begin, ensure you have the following:

- An AWS account with EC2 access.
- Basic knowledge of the Linux command line interface (CLI).
- A registered domain name and access to DNS settings.
- An FTP client (e.g., FileZilla).

## Installation
Follow these steps to set up your web hosting environment:

### 1. Launch an EC2 Instance
- Start an EC2 instance using a Linux AMI.
- Configure security groups to allow SSH (port 22), HTTP (port 80), and HTTPS (port 443) traffic.

### 2. Install the Web Server (Apache)
- SSH into your EC2 instance.
- Update the system and install Apache:
  ```bash
  sudo yum update -y
  sudo yum install httpd -y
  sudo systemctl start httpd
  sudo systemctl enable httpd
  ```

### 3. Configure the FTP Server (vsftpd)
- Install and configure vsftpd for secure file transfers:
  ```bash
  sudo yum install vsftpd -y
  sudo systemctl restart vsftpd
  ```

### 4. Get a Free Domain
- Register at InfinityFree and claim a free domain.

### 5. Associate Your External Domain
- Log in to your domain registrar's dashboard.
- Navigate to the DNS management or settings page.
- Create an A record with the public IP address of your EC2 instance.
- Save the changes to point your domain to your AWS-hosted website.

### 6. Obtain an SSL Certificate
- Install certbot and set up SSL:
  ```bash
  sudo yum install certbot python3-certbot-apache -y
  sudo certbot --apache
  ```

## Usage
- Access your website by visiting your domain.
- Connect via FTP using your EC2 instance's IP, username, and password.

## Contributing
Contributions are encouraged! Refer to CONTRIBUTING.md for guidelines.

## License
This project is licensed under the MIT License. See LICENSE for details.







