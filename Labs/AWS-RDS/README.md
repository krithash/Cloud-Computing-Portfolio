# Amazon RDS (MySQL) – Database Setup and EC2 Client Configuration

## Objective

Create and configure an Amazon Relational Database Service (RDS) instance using MySQL. Launch an Amazon EC2 instance to act as a database client and install the MariaDB client package to prepare the environment for connecting to the RDS database.

Understand managed relational databases, database instance configuration, Single-AZ deployment, instance classes, EC2 client setup, and MySQL client installation.

---

# Services and Technologies Used

## AWS Services

- Amazon RDS
- Amazon EC2
- Amazon VPC
- Security Groups

## Database and Operating System Technologies

- MySQL
- MariaDB Client
- Amazon Linux
- Linux Package Manager (DNF)

## Concepts

- Relational Database Management System (RDBMS)
- Managed Database Service
- DB Instance
- Database Engine
- Database Instance Identifier
- Master Username
- Master Password
- Single-AZ Deployment
- Burstable Instance Classes
- Database Client
- MySQL Client
- Database Connectivity

---

# Architecture Diagram

```text
                   AWS Cloud
                       |
              +--------+--------+
              |                 |
       +------+-------+  +------+-------+
       | Amazon RDS   |  | Amazon EC2   |
       |              |  |              |
       | MySQL        |  | RDS-Client   |
       | Database     |  |              |
       | Instance     |  | Amazon Linux |
       |              |  |              |
       | Single-AZ    |  | MariaDB      |
       | Deployment   |  | Client       |
       +--------------+  +--------------+
                              |
                       MySQL Client
                       Installation
```

---

# Architecture Description

- An Amazon RDS database instance was created using the MySQL database engine.
- The database was configured using the Full Configuration method.
- The Free Tier template was selected during database creation.
- Single-AZ DB Instance Deployment was selected for availability and durability.
- A master username and password were configured for database authentication.
- A burstable instance class was selected for the database instance.
- A separate Amazon EC2 instance named `RDS-Client` was launched.
- Amazon Linux was selected as the operating system for the EC2 instance.
- The EC2 instance was configured using the `t2.micro` instance type.
- The MariaDB 10.5 client package was installed on the EC2 instance.
- The installed MySQL-compatible client version was verified using the `mysql --version` command.

---

# Project Overview

This practical demonstrates the creation and configuration of an Amazon RDS database using MySQL and the setup of a separate Amazon EC2 instance to act as a database client.

Amazon RDS provides a managed relational database environment, eliminating the need to manually manage the underlying database infrastructure.

An EC2 instance was launched separately with Amazon Linux, and the MariaDB client package was installed to prepare the environment for database connectivity.

The practical provides hands-on experience with Amazon RDS, MySQL database configuration, EC2 instance deployment, Linux package installation, and database client tools.

---

# Implementation

## 1. Create Amazon RDS MySQL Database

Created a managed relational database instance using Amazon RDS.

### Activities Performed

- Opened **Amazon RDS → Databases**.
- Selected **Create Database**.
- Selected **Full Configuration**.
- Engine Type: `MySQL`
- Database Creation Method: `Full Configuration`
- Template: `Free Tier`
- Availability and Durability: `Single-AZ DB Instance Deployment (1 Instance)`
- Entered the DB Instance Identifier.
- Master Username: `krithash`
- Credentials Management: `Self Managed`
- Entered the master password and confirmed it.
- Selected **Burstable Classes**.
- Selected the required DB Instance Type.
- Selected **Create Database**.
- Waited until the database status changed to `Available`.

### Outcome

Successfully created an Amazon RDS instance using the MySQL database engine with a Single-AZ deployment.

The database instance became available for subsequent database operations.

---

## 2. Launch EC2 Instance for RDS Client

Launched a separate Amazon EC2 instance to prepare an environment for accessing the RDS database.

### Activities Performed

- Opened **EC2 → Instances**.
- Selected **Launch Instance**.
- Name: `RDS-Client`
- Selected **Amazon Linux** as the operating system.
- Instance Type: `t2.micro`
- Configured the required instance settings.
- Selected **Launch Instance**.
- Waited until the instance was running.

### Outcome

Successfully launched an EC2 instance named `RDS-Client` using Amazon Linux and the `t2.micro` instance type.

---

## 3. Connect to EC2 Instance

Connected to the newly launched EC2 instance to perform Linux-level operations.

### Activities Performed

- Opened **EC2 → Instances**.
- Selected the `RDS-Client` instance.
- Selected **Connect**.
- Established a connection to the EC2 instance.
- Switched to the root user using:

```bash
sudo su
```

### Outcome

Successfully accessed the EC2 instance and obtained root-level privileges to execute the required installation commands.

---

## 4. Install MariaDB Client

Installed the MariaDB 10.5 client package on the Amazon Linux EC2 instance.

### Activities Performed

Executed the following command:

```bash
dnf install mariadb105 -y
```

**Command Explanation:**

- `dnf` – Package manager used in Amazon Linux 2023.
- `install` – Installs the specified package.
- `mariadb105` – MariaDB 10.5 client package.
- `-y` – Automatically confirms installation prompts.

### Outcome

Successfully installed the MariaDB 10.5 client package on the EC2 instance.

---

## 5. Verify MySQL Client Installation

Verified whether the MySQL-compatible client was installed successfully.

### Activities Performed

Executed the following command:

```bash
mysql --version
```

### Outcome

Successfully verified the installed MySQL-compatible client version.

The EC2 instance was prepared with the necessary client software for subsequent RDS database connectivity.

---

# Key Learnings

- Amazon Relational Database Service (RDS)
- Managed Relational Database Services
- MySQL Database Engine
- RDS Database Instance Creation
- Full Configuration Method
- Free Tier Database Template
- Single-AZ Deployment
- Database Instance Identifier
- Master Username and Password
- Self-Managed Credentials
- Burstable Instance Classes
- Amazon EC2 Instance Launch
- Amazon Linux
- Linux Root User
- DNF Package Manager
- MariaDB Client Installation
- MySQL Client Version Verification
- EC2 as a Database Client

---

# Skills Demonstrated

- Amazon RDS Configuration
- MySQL Database Setup
- Database Instance Deployment
- AWS EC2 Instance Configuration
- Amazon Linux Administration
- Linux Command-Line Operations
- Package Installation Using DNF
- MariaDB Client Configuration
- Database Client Environment Setup
- AWS Cloud Services

---

# Conclusion

Successfully created an Amazon RDS database instance using the MySQL database engine with a Single-AZ deployment.

A separate Amazon EC2 instance was launched using Amazon Linux to act as the database client. The MariaDB 10.5 client package was installed, and its version was verified using the MySQL version command.

This practical provided hands-on experience with managed database services, MySQL configuration, EC2 deployment, Linux administration, and database client installation.
