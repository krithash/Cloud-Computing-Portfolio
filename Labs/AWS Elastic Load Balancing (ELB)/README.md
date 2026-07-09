AWS Elastic Load Balancing (ELB)
Objective

Learn and implement the four types of AWS Elastic Load Balancers—Classic Load Balancer (CLB), Application Load Balancer (ALB), Network Load Balancer (NLB), and Gateway Load Balancer (GWLB). Configure EC2 instances as backend servers, distribute incoming traffic, and understand load balancing concepts, target groups, health checks, and high availability across multiple Availability Zones.

Services and Technologies Used
AWS Services
Amazon EC2
Elastic Load Balancing (ELB)
Classic Load Balancer (CLB)
Application Load Balancer (ALB)
Network Load Balancer (NLB)
Gateway Load Balancer (GWLB)
Target Groups
Security Groups
Amazon VPC
Networking Concepts
HTTP
TCP
Health Checks
Target Registration
High Availability
Multi-AZ Deployment
Architecture Diagram
                    Internet Users
                          |
                    DNS Endpoint
                          |
             +---------------------------+
             | Elastic Load Balancer     |
             | (CLB / ALB / NLB / GWLB)  |
             +---------------------------+
                   |               |
          Health Checks      Traffic Distribution
                   |               |
         -------------------------------
         |                             |
   +-------------+               +-------------+
   | EC2 Instance|               | EC2 Instance|
   |   Web-01    |               |   Web-02    |
   +-------------+               +-------------+
Architecture Description
Multiple Amazon EC2 instances were launched to host web applications.
A load balancer was created to distribute incoming client requests.
Health checks continuously monitored backend instance availability.
Target instances were automatically registered with the load balancer.
Traffic was distributed among healthy instances.
High availability was achieved by deploying resources across multiple Availability Zones.
Project Overview

This project demonstrates the implementation of AWS Elastic Load Balancing to improve application availability, scalability, and fault tolerance. Different ELB types were configured to understand their use cases, routing mechanisms, health monitoring, and traffic distribution capabilities. Backend EC2 instances hosted identical web pages, allowing verification of load balancing through the DNS endpoint.

Implementation
1. EC2 Instance Preparation

Multiple EC2 instances were launched to act as backend web servers.

Activities Performed
Created multiple EC2 instances.
Renamed instances for easy identification.
Installed Apache Web Server.
Created simple HTML webpages.
Verified web server accessibility.
Outcome

Successfully prepared backend web servers for load balancing.

2. Classic Load Balancer (CLB)

Configured a Classic Load Balancer to distribute HTTP traffic across EC2 instances.

Activities Performed
Created a Classic Load Balancer.
Selected Internet-facing scheme.
Chose multiple Availability Zones.
Configured HTTP Listener (Port 80).
Created Security Group.
Configured Health Check.
Registered EC2 instances.
Accessed the DNS endpoint.
Outcome

Traffic was successfully distributed among backend EC2 instances using CLB.

3. Application Load Balancer (ALB)

Configured an Application Load Balancer using Target Groups for Layer 7 HTTP routing.

Activities Performed
Created an Application Load Balancer.
Configured Listener on Port 80.
Created Target Group.
Registered EC2 instances.
Verified Target Health.
Accessed the ALB DNS endpoint.
Outcome

Successfully implemented Layer 7 load balancing with Application Load Balancer.

4. Network Load Balancer (NLB)

Configured a Network Load Balancer for high-performance Layer 4 traffic distribution.

Activities Performed
Created a Network Load Balancer.
Configured TCP Listener.
Created Target Group.
Registered backend instances.
Verified healthy targets.
Tested NLB DNS endpoint.
Outcome

Successfully configured Layer 4 load balancing with low latency.

5. Gateway Load Balancer (GWLB)

Configured a Gateway Load Balancer for transparent deployment of virtual network appliances.

Activities Performed
Created Gateway Load Balancer.
Configured Gateway Listener.
Created Target Group.
Registered appliance instances.
Verified healthy targets.
Monitored GWLB metrics.
Outcome

Successfully deployed Gateway Load Balancer and validated target health and traffic processing.

Key Learnings
Elastic Load Balancing Concepts
Classic Load Balancer
Application Load Balancer
Network Load Balancer
Gateway Load Balancer
Target Groups
Health Checks
Listener Configuration
Security Groups
Traffic Distribution
High Availability
Multi-AZ Deployment
Fault Tolerance
Skills Demonstrated
Amazon EC2 Administration
Elastic Load Balancing
Classic Load Balancer Configuration
Application Load Balancer Configuration
Network Load Balancer Configuration
Gateway Load Balancer Configuration
Target Group Management
Health Check Configuration
High Availability Design
AWS Networking
Cloud Infrastructure Deployment
Conclusion

Successfully implemented AWS Elastic Load Balancing by configuring Classic, Application, Network, and Gateway Load Balancers with multiple Amazon EC2 instances. The project demonstrated how load balancers distribute incoming traffic, monitor backend instance health, improve application availability, and provide fault tolerance across multiple Availability Zones. This hands-on lab strengthened practical knowledge of AWS networking, scalable cloud architectures, and high-availability application deployment.
