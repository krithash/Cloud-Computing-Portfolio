# AWS Elastic Load Balancing (ELB)

## Objective

Create and configure AWS Elastic Load Balancers (Classic Load Balancer, Application Load Balancer, Network Load Balancer, and Gateway Load Balancer) to distribute incoming traffic across multiple Amazon EC2 instances. Learn load balancing concepts, health checks, target groups, and high availability using multiple Availability Zones.

---

# Services and Technologies Used

## AWS Services

- Amazon EC2
- Elastic Load Balancing (ELB)
- Classic Load Balancer (CLB)
- Application Load Balancer (ALB)
- Network Load Balancer (NLB)
- Gateway Load Balancer (GWLB)
- Target Groups
- Security Groups
- Amazon VPC

## Networking Concepts

- HTTP
- TCP
- Health Checks
- Target Registration
- Traffic Distribution
- High Availability
- Multi-AZ Deployment

---

# Architecture Diagram

```text
                    Internet Users
                          |
                          |
                    ELB DNS Endpoint
                          |
          +--------------------------------+
          | Elastic Load Balancer (ELB)    |
          | CLB / ALB / NLB / GWLB         |
          +--------------------------------+
                  |                |
          Health Checks     Load Balancing
                  |                |
          ------------------------------
          |                            |
    +--------------+            +--------------+
    | EC2 Instance |            | EC2 Instance |
    |   Web-01     |            |   Web-02     |
    +--------------+            +--------------+
```

---

# Architecture Description

- Multiple Amazon EC2 instances were launched to host web applications.
- Elastic Load Balancer was configured to distribute incoming client requests.
- Health checks continuously monitored backend instance availability.
- Only healthy EC2 instances received client traffic.
- Resources were deployed across multiple Availability Zones to improve availability and fault tolerance.
- Users accessed the application through the Load Balancer DNS endpoint instead of directly accessing EC2 instances.

---

# Project Overview

This project demonstrates the implementation of AWS Elastic Load Balancing (ELB) to improve application scalability, availability, and fault tolerance. Multiple EC2 instances were configured as backend web servers, and different types of load balancers were deployed to understand their functionality, traffic routing mechanisms, and monitoring capabilities.

---

# Implementation

## 1. EC2 Instance Preparation

Multiple Amazon EC2 instances were created to serve as backend web servers.

### Activities Performed

- Created multiple EC2 instances.
- Renamed the instances.
- Installed Apache Web Server.
- Created sample HTML webpages.
- Verified web server accessibility.

### Outcome

Successfully prepared backend EC2 instances for load balancing.

---

## 2. Classic Load Balancer (CLB)

Configured a Classic Load Balancer to distribute HTTP requests across EC2 instances.

### Activities Performed

- Created a Classic Load Balancer.
- Selected Internet-facing scheme.
- Selected multiple Availability Zones.
- Configured HTTP Listener (Port 80).
- Created a Security Group.
- Configured Health Check.
- Registered EC2 instances.
- Tested the Load Balancer DNS endpoint.

### Outcome

Traffic was successfully distributed among healthy EC2 instances using Classic Load Balancer.

---

## 3. Application Load Balancer (ALB)

Configured an Application Load Balancer using Target Groups for Layer 7 routing.

### Activities Performed

- Created an Application Load Balancer.
- Configured HTTP Listener.
- Created a Target Group.
- Registered EC2 instances.
- Verified healthy targets.
- Tested the ALB DNS endpoint.

### Outcome

Successfully implemented Layer 7 load balancing using Application Load Balancer.

---

## 4. Network Load Balancer (NLB)

Configured a Network Load Balancer to distribute TCP traffic with low latency.

### Activities Performed

- Created a Network Load Balancer.
- Configured TCP Listener.
- Created a Target Group.
- Registered EC2 instances.
- Verified healthy targets.
- Tested the NLB DNS endpoint.

### Outcome

Successfully implemented high-performance Layer 4 load balancing using Network Load Balancer.

---

## 5. Gateway Load Balancer (GWLB)

Configured a Gateway Load Balancer to deploy and manage virtual network appliances.

### Activities Performed

- Created a Gateway Load Balancer.
- Configured Gateway Listener.
- Created a Target Group.
- Registered appliance instances.
- Verified target health.
- Monitored Gateway Load Balancer metrics.

### Outcome

Successfully configured Gateway Load Balancer and validated traffic processing through healthy targets.

---

# Key Learnings

- Elastic Load Balancing Concepts
- Classic Load Balancer (CLB)
- Application Load Balancer (ALB)
- Network Load Balancer (NLB)
- Gateway Load Balancer (GWLB)
- Target Groups
- Listener Configuration
- Health Checks
- Security Groups
- Traffic Distribution
- High Availability
- Multi-AZ Architecture
- Fault Tolerance

---

# Skills Demonstrated

- Amazon EC2 Administration
- AWS Elastic Load Balancing
- Classic Load Balancer Configuration
- Application Load Balancer Configuration
- Network Load Balancer Configuration
- Gateway Load Balancer Configuration
- Target Group Management
- Health Check Configuration
- AWS Networking
- High Availability Design
- Cloud Infrastructure Deployment

---

# Conclusion

Successfully deployed and configured AWS Elastic Load Balancing services, including Classic Load Balancer, Application Load Balancer, Network Load Balancer, and Gateway Load Balancer. The project demonstrated how ELB distributes traffic across multiple EC2 instances, performs health monitoring, improves application availability, and provides fault tolerance through multi-Availability Zone deployments. This hands-on implementation strengthened practical skills in AWS networking, cloud infrastructure, and scalable application deployment.
