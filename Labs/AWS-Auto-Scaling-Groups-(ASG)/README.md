# AWS Auto Scaling Groups (ASG)

## Objective

Deploy and configure AWS Auto Scaling Groups (ASG) to automatically launch, maintain, monitor, and replace Amazon EC2 instances, ensuring application availability, fault tolerance, and high availability. Learn how Amazon Machine Images (AMI), Launch Templates, and Auto Scaling Groups work together to build self-healing cloud infrastructure capable of automatically recovering from instance failures.

---

# Services and Technologies Used

## AWS Services

- Amazon EC2
- Amazon Machine Image (AMI)
- Launch Templates
- Auto Scaling Groups (ASG)
- Amazon VPC
- Security Groups

## Infrastructure Concepts

- Amazon Machine Images (AMI)
- Launch Templates
- Auto Scaling Groups
- Desired Capacity
- Minimum Capacity
- Maximum Capacity
- Self-Healing Infrastructure
- Automatic Instance Replacement
- Instance Health Monitoring
- High Availability
- Fault Tolerance
- Multi-Availability Zone (Multi-AZ) Deployment

---

# Architecture Diagram

```text
                         Internet Users
                                |
                                |
                    Application Requests
                                |
                 +------------------------------+
                 |   Auto Scaling Group (ASG)   |
                 +------------------------------+
                          Desired Capacity = 2
                         /                    \
                        /                      \
              +----------------+      +----------------+
              | EC2 Instance 1 |      | EC2 Instance 2 |
              +----------------+      +----------------+
                      |                       |
          Continuous Health Monitoring by ASG
                      |
          If an Instance Becomes Unhealthy
                      |
          Automatically Launch Replacement
                      |
              +----------------+
              | New EC2 Instance|
              +----------------+
```

---

# Architecture Description

A base Amazon EC2 instance was created and configured with the required web application. After verifying its functionality, a custom Amazon Machine Image (AMI) was created to preserve the operating system, application, and configuration.

A Launch Template was then created using the custom AMI, enabling AWS to automatically provision identical EC2 instances whenever required.

An Auto Scaling Group (ASG) was configured using the Launch Template. The Auto Scaling Group maintained the desired number of EC2 instances across multiple Availability Zones and continuously monitored instance health.

Whenever an EC2 instance was manually terminated or became unhealthy, the Auto Scaling Group automatically detected the failure and launched a replacement instance, ensuring uninterrupted application availability and infrastructure resilience.

---

# Project Overview

This project demonstrates the implementation of AWS Auto Scaling Groups (ASG) to build highly available and fault-tolerant cloud infrastructure. A custom Amazon Machine Image (AMI) was created from a configured EC2 instance and used within a Launch Template to automate future instance deployments.

The Auto Scaling Group continuously monitored instance health and automatically maintained the configured desired capacity by replacing failed or terminated instances without requiring manual intervention. This implementation highlights one of the core cloud principles of building self-healing and resilient infrastructure capable of maintaining application availability even during unexpected failures.

---

# Implementation

## 1. EC2 Instance Preparation

A base Amazon EC2 instance was created and configured to host a sample web application.

### Activities Performed

- Created an Amazon EC2 instance
- Installed Apache Web Server
- Configured sample HTML webpage
- Verified web server accessibility

### Outcome

Successfully prepared the base EC2 instance for creating a reusable Amazon Machine Image (AMI).

---

## 2. Amazon Machine Image (AMI)

Created a custom Amazon Machine Image from the configured EC2 instance.

### Activities Performed

- Created an EC2 Instance.
- Navigated to **EC2 Dashboard**.
- Selected the configured EC2 instance.
- Chose **Actions → Image and Templates → Create Image**.
- Entered an image name.
- Clicked **Create Image**.
- Navigated to **AMIs → My AMIs**.
- Verified the AMI status changed to **Available**.

### Outcome

Successfully created a reusable machine image that preserves the operating system, installed software, web server configuration, and application data for future deployments.

---

## 3. Launch Template

Created a Launch Template using the custom AMI.

### Activities Performed

- Navigated to **EC2 Dashboard → Launch Templates**.
- Clicked **Create Launch Template**.
- Entered a Launch Template name.
- Selected the custom Amazon Machine Image (AMI).
- Selected the EC2 Instance Type.
- Configured the Key Pair.
- Configured the Security Group.
- Created the Launch Template.

### Outcome

Successfully created a reusable deployment template capable of automatically launching identical EC2 instances whenever required.

---

## 4. Auto Scaling Group (ASG)

Configured an Auto Scaling Group using the Launch Template.

### Activities Performed

- Navigated to **EC2 → Auto Scaling Groups**.
- Clicked **Create Auto Scaling Group**.
- Entered the Auto Scaling Group name.
- Selected the previously created Launch Template.
- Configured the Default VPC.
- Selected multiple Availability Zones and Subnets.
- Chose **Do not attach to a Load Balancer**.
- Configured Desired Capacity.
- Configured Minimum Capacity.
- Configured Maximum Capacity.
- Selected **No Scaling Policies**.
- Reviewed all configurations.
- Created the Auto Scaling Group.

### Outcome

Successfully deployed an Auto Scaling Group capable of automatically maintaining the desired number of EC2 instances.

---

## 5. Auto Scaling Validation

Validated the automatic recovery capability of the Auto Scaling Group.

### Activities Performed

- Verified EC2 instances launched by the Auto Scaling Group.
- Navigated to **EC2 → Instances**.
- Confirmed that instances were automatically launched from the custom AMI.
- Manually terminated one running EC2 instance.
- Monitored Auto Scaling Group Activity History.
- Observed the automatic launch of a replacement EC2 instance.
- Verified that the desired capacity was maintained.

### Outcome

Successfully demonstrated AWS Auto Scaling's self-healing capability by automatically replacing failed or terminated instances without manual intervention.

---

# Key Learnings

- Amazon Machine Images (AMI)
- Launch Templates
- Auto Scaling Groups (ASG)
- Desired Capacity
- Minimum Capacity
- Maximum Capacity
- Automatic Instance Replacement
- EC2 Health Monitoring
- Self-Healing Infrastructure
- High Availability
- Fault Tolerance
- Multi-Availability Zone Deployment
- Infrastructure Automation

---

# Skills Demonstrated

- Amazon EC2 Administration
- Amazon Machine Image (AMI) Creation
- Launch Template Configuration
- AWS Auto Scaling Groups (ASG)
- EC2 Instance Lifecycle Management
- AWS Infrastructure Automation
- High Availability Architecture
- Fault Tolerance Design
- Self-Healing Cloud Infrastructure
- AWS Cloud Operations
- Cloud Infrastructure Deployment

---

# Conclusion

Successfully deployed and configured AWS Auto Scaling Groups (ASG) to automate EC2 instance provisioning, health monitoring, and automatic recovery. By integrating Amazon Machine Images (AMI), Launch Templates, and Auto Scaling Groups, the infrastructure automatically maintained the desired number of running EC2 instances while replacing failed or manually terminated instances without requiring administrative intervention.

This hands-on implementation demonstrated how AWS Auto Scaling enhances infrastructure resilience, improves application availability, reduces operational effort, and enables organizations to build scalable, fault-tolerant, and self-healing cloud environments capable of maintaining continuous service availability.

---
