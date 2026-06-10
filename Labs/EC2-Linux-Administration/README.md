# AWS EC2 Linux Administration and Apache Website Hosting

## Objective

Deploy and administer a Linux-based Amazon EC2 instance, perform Linux system administration tasks such as hostname configuration and user management, and host a static website using the Apache HTTP Server.

---

## Services and Technologies Used

### AWS Services

* Amazon EC2
* Security Groups
* EC2 Key Pairs

### Operating System

* Amazon Linux

### Networking

* Secure Shell (SSH)
* HTTP

### Web Services

* Apache HTTP Server (httpd)

---

## Architecture Diagram

```text
                        Internet
                            |
                            |
                    +----------------+
                    | Security Group |
                    | 22 (SSH)       |
                    | 80 (HTTP)      |
                    +----------------+
                            |
                            |
                    +----------------+
                    | Linux EC2      |
                    | Amazon Linux   |
                    +----------------+
                      |            |
                      |            |
                 SSH Access     Apache Server
                      |            |
                      |            |
                EC2 User      index.html
                              Website Files
                                   |
                                   |
                                   v
                          http://Public-IP
                                   |
                                   |
                           End User Browser
```

### Architecture Description

* A Linux-based Amazon EC2 instance was deployed in AWS.
* A Security Group was configured to allow SSH (Port 22) and HTTP (Port 80) traffic.
* The EC2 instance was administered through EC2 Instance Connect.
* Linux administration tasks such as hostname modification and user management were performed.
* Apache HTTP Server was installed and configured.
* A static HTML webpage was deployed and served through Apache.
* The hosted webpage was successfully accessed using the EC2 instance's public IPv4 address.

---

## Project Overview

This project demonstrates the deployment and administration of a Linux server environment on AWS. The EC2 instance was configured for secure remote access, hostname management and user administration tasks were performed, and a static website was hosted using Apache HTTP Server.

---

## Implementation

### 1. Linux EC2 Deployment

A Linux EC2 instance was launched using a Free Tier eligible Amazon Linux AMI. A new RSA key pair was generated for authentication, and a Security Group was configured to allow SSH access.

#### Outcome

* Successfully launched a Linux EC2 instance.
* Assigned a public IPv4 address.
* Enabled secure administrative access.

---

### 2. Hostname Verification and Modification

The existing hostname was verified using Linux terminal commands. The hostname was then modified using the hostnamectl utility and verified after the change.

#### Activities Performed

* Verified the current hostname.
* Updated the hostname to a custom value.
* Confirmed successful hostname modification.

#### Commands Used

```bash
hostname

sudo hostnamectl set-hostname Linux-Server

hostname
```

#### Outcome

* Successfully customized and verified the Linux server hostname.

---

### 3. Linux User Administration

A new user account was created and assigned administrative privileges using the wheel group. User switching was then performed to verify successful account creation and access permissions.

#### Activities Performed

* Created a new user account.
* Configured a password for the user.
* Granted sudo privileges.
* Switched to the newly created user account.

#### Commands Used

```bash
sudo adduser student

sudo passwd student

sudo usermod -aG wheel student

su - student
```

#### Outcome

* Successfully implemented Linux user and privilege management.

---

### 4. Apache Web Server Installation and Website Hosting

HTTP access was enabled through the Security Group by allowing inbound traffic on Port 80. Apache HTTP Server was installed, configured, and started. A custom HTML webpage was then created and deployed.

#### Activities Performed

* Installed Apache HTTP Server.
* Started and enabled the Apache service.
* Created a custom HTML webpage.
* Deployed the webpage to the Apache web root directory.
* Verified public accessibility through a browser.

#### Commands Used

```bash
sudo su

yum install httpd -y

systemctl start httpd

systemctl enable httpd

cd /var/www/html

mkdir website

cd website

touch index.html

echo "<h1>Hello from Linux EC2 Website</h1>" > index.html

cat index.html

cp index.html /var/www/html
```

#### Outcome

* Successfully hosted a static website on AWS Linux EC2.

---

## Key Learnings

* Amazon EC2 deployment and configuration
* Linux server administration in the cloud
* SSH-based remote access
* Security Group configuration and management
* Linux user and privilege management
* Hostname configuration and verification
* Apache HTTP Server installation and configuration
* Static website hosting on Linux
* Public accessibility of cloud-hosted services

---

## Skills Demonstrated

* AWS EC2
* Linux Administration
* SSH
* Security Group Management
* User and Permission Management
* Apache HTTP Server Administration
* Website Hosting
* Cloud Infrastructure Management

---

## Conclusion

Successfully deployed and administered a Linux-based Amazon EC2 environment on AWS. The project demonstrated practical cloud and Linux administration skills including hostname management, user administration, privilege assignment, Apache web server configuration, and static website hosting. The final outcome was a publicly accessible website hosted on an AWS Linux EC2 instance.
