# AWS Web Hosting with Linux Web Server, FTP, Free Domain with SSL

## Description
This project demonstrates how to set up a web hosting environment on AWS using a Linux-based web server. It includes configurations for hosting a website, enabling FTP access, associating an external domain, and securing the website with SSL/TLS encryption.

## Table of Contents
- Features
- Prerequisites
- Installation
- Usage
- Contributing
- License

## Features
- **Linux Web Server**: Utilizes an Amazon EC2 instance running a Linux distribution as the web server.
- **FTP Access**: Configures vsftpd (Very Secure FTP Daemon) for secure FTP access to the server.
- **External Domain**: Guides the setup of DNS records to associate an external domain with the EC2 instance.
- **SSL/TLS Encryption**: Implements SSL/TLS encryption using a free SSL certificate for secure HTTPS connections.

## Prerequisites
- An AWS account with access to the EC2 service.
- Basic knowledge of Linux command-line interface.
- A registered domain name with access to DNS management settings.
- An FTP client for accessing the server (e.g., FileZilla).

## Installation
### Launch EC2 Instance
- Launch an Amazon EC2 instance with a Linux-based AMI (Amazon Machine Image).
- Configure security groups to allow inbound traffic on ports 22 (SSH), 80 (HTTP), and 443 (HTTPS).

### Install Web Server
- Connect to the EC2 instance via SSH.
- Install Apache HTTP Server:
  ```bash
  sudo yum update -y
  sudo yum install httpd -y
  sudo systemctl start httpd
  sudo systemctl enable httpd

Configure FTP Server- Install vsftpd:

sudo yum install vsftpd -y

- Configure vsftpd according to security requirements.
- Restart vsftpd:

sudo systemctl restart vsftpd

Associate External Domain- In your domain registrar's dashboard, create an "A" record pointing to the EC2 instance's public IP address.
Obtain SSL Certificate- Generate a free SSL certificate using Let's Encrypt or similar service.
- Configure Apache to use the SSL certificate:

# Install certbot
sudo yum install certbot python3-certbot-apache -y
# Obtain and install SSL certificate
sudo certbot --apache

Usage Access Website- Enter your domain name in a web browser to access the website hosted on the EC2 instance.
FTP Access- Use an FTP client to connect to the server using the instance's public IP address, username, and password.

ContributingContributions are welcome! 
Please follow the guidelines outlined in CONTRIBUTING.md.
LicenseThis project is licensed under the MIT License. See the LICENSE file for more details.




