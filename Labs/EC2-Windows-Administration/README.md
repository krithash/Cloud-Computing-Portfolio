# AWS EC2 Windows Administration and IIS Website Hosting

## Objective

Deploy and administer a Windows-based Amazon EC2 instance, perform Windows Server management tasks, create and manage local administrator accounts, modify the system hostname, and host a static website using Internet Information Services (IIS).

---

## Services and Technologies Used

### AWS Services

* Amazon EC2
* Security Groups
* EC2 Key Pairs

### Operating System

* Microsoft Windows Server

### Networking

* Remote Desktop Protocol (RDP)
* HTTP

### Web Services

* Internet Information Services (IIS)

---

## Architecture Diagram

```text
                        Internet
                            |
                            |
                    +----------------+
                    | Security Group |
                    | 3389 (RDP)     |
                    | 80 (HTTP)      |
                    +----------------+
                            |
                            |
                    +----------------+
                    | Windows EC2    |
                    | Windows Server |
                    +----------------+
                      |            |
                      |            |
               RDP Access      IIS Web Server
                      |            |
                      |            |
              Administrator     index.html
                 Login         Website Files
                                   |
                                   |
                                   v
                          http://Public-IP
                                   |
                                   |
                           End User Browser
```

### Architecture Description

* A Windows-based Amazon EC2 instance was deployed in AWS.
* A Security Group was configured to allow RDP (Port 3389) and HTTP (Port 80) traffic.
* The EC2 instance was remotely administered using Remote Desktop Protocol (RDP).
* Windows Server administration tasks such as user creation and hostname modification were performed.
* Internet Information Services (IIS) was installed and configured.
* A static HTML webpage was deployed inside the IIS web root directory.
* The hosted webpage was successfully accessed using the EC2 instance's public IPv4 address.

---

## Project Overview

This project demonstrates the deployment and administration of a Windows Server environment on AWS. The EC2 instance was configured for secure remote access, local user management was performed, system hostname configuration was verified and modified, and a static website was hosted using IIS.

---

## Implementation

### 1. Windows EC2 Deployment

A Windows EC2 instance was launched using a Free Tier eligible Amazon Machine Image (AMI). A new RSA key pair was generated for secure authentication, and a Security Group was configured to allow Remote Desktop Protocol (RDP) access.

#### Outcome

* Successfully launched a Windows EC2 instance.
* Assigned a public IPv4 address for remote administration.
* Configured secure access using an RSA key pair.

---

### 2. Remote Administration Using RDP

The Administrator password was retrieved and decrypted using the downloaded PEM key pair. Remote Desktop Connection (mstsc) was then used to access the Windows Server environment.

#### Outcome

* Successfully established an RDP connection.
* Obtained full administrative access to the Windows Server instance.

---

### 3. Local User Administration

A new local user account was created using the Local Users and Groups management console. The account was added to the Administrators group and verified by logging into the server using the newly created user credentials.

#### Activities Performed

* Created a new local user account.
* Assigned Administrator privileges.
* Verified successful user creation.
* Logged in using the newly created administrative account.

#### Outcome

* Successfully implemented local user management and access control within Windows Server.

---

### 4. Hostname Verification and Modification

The existing hostname was verified using Command Prompt. System Properties was then used to modify the hostname, followed by a system restart to apply the changes.

#### Activities Performed

* Verified the existing hostname.
* Modified the hostname to a custom value.
* Restarted the system.
* Confirmed successful hostname update.

#### Outcome

* Successfully customized and verified the server hostname.

---

### 5. IIS Web Server Installation and Website Hosting

HTTP access was enabled by configuring an inbound Security Group rule for Port 80. The IIS Web Server role was installed, and a custom HTML page was deployed within the IIS web root directory.

The hosted website was then accessed through the EC2 instance's public IPv4 address.

#### Activities Performed

* Configured HTTP inbound access.
* Installed IIS Web Server.
* Created and deployed an HTML webpage.
* Hosted the webpage through the EC2 instance.
* Verified successful public access using a web browser.

#### Outcome

* Successfully hosted a static website on AWS Windows EC2.

---

## Key Learnings

* Amazon EC2 deployment and configuration
* Windows Server administration in the cloud
* Remote administration using RDP
* Security Group configuration and management
* Local user and administrator account management
* Hostname configuration and verification
* IIS installation and configuration
* Static website hosting on Windows Server
* Public accessibility of cloud-hosted services

---

## Skills Demonstrated

* AWS EC2
* Windows Server Administration
* Remote Desktop Protocol (RDP)
* Security Group Management
* IIS Web Server Administration
* Website Hosting
* Cloud Infrastructure Management
* Basic System Administration

---

## Conclusion

Successfully deployed and administered a Windows Server environment on AWS EC2. The project demonstrated practical cloud administration skills including remote access configuration, user management, hostname customization, security group management, and IIS-based website hosting. The final outcome was a publicly accessible website hosted on a Windows Server running in the AWS Cloud.

