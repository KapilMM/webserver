# AWS Linux Web Hosting with External Free Domain, FTP, and SSL

## Description
Set up a robust web hosting environment on AWS with this comprehensive guide. Utilize a Linux web server, enable FTP access, connect an external domain, and secure your site with SSL/TLS encryption.

## Table of Contents
1. Features
2. Prerequisites
3. Installation
4. Usage
5. Contributing
6. License

## Features
- **Linux Web Server**: Deploy on an Amazon EC2 instance with a Linux OS.
- **FTP Access**: Secure file transfer with vsftpd.
- **External Domain**: Link your own domain to the AWS instance.
- **SSL/TLS Encryption**: Protect your site with a free SSL certificate.

## Prerequisites
- AWS account and EC2 access.
- Linux CLI knowledge.
- Domain name and DNS access.
- FTP client (e.g., FileZilla).

## Installation
### Launch EC2 Instance
- Start an EC2 instance with a Linux AMI.
- Set security groups for SSH (22), HTTP (80), HTTPS (443).

### Install Web Server
- SSH into your EC2 instance.
- Update and install Apache:
  ```bash
  sudo yum update -y
  sudo yum install httpd -y
  sudo systemctl start httpd
  sudo systemctl enable httpd

Configure FTP Server- Install and configure vsftpd for secure transfers:

sudo yum install vsftpd -y
sudo systemctl restart vsftpd

Get a Free Domain- Register at InfinityFree and claim a free domain.
Associate Domain with AWS- Update DNS "A" record to EC2's IP at your domain registrar.
Obtain SSL Certificate- Install certbot and run it to set up SSL:

sudo yum install certbot python3-certbot-apache -y
sudo certbot --apache

UsageAccess Website- Visit your domain to see your AWS-hosted site.
FTP Access- Connect via FTP using your EC2's IP, username, and password.
Contributing- Contributions are encouraged. See CONTRIBUTING.md for guidelines.
License- MIT License. Refer to LICENSE for details.







