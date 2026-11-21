**AWS Custom VPC Network – Cloud Computing Internship**

Project Overview

This project focuses on designing and implementing a custom Virtual Private Cloud (VPC) network using Amazon Web Services (AWS).

The objective is to build a secure and segmented network infrastructure using public and private subnets distributed across multiple Availability Zones.

The project demonstrates practical AWS networking concepts, including VPC creation, subnet configuration, Internet Gateway, route tables, security groups, EC2 deployment and connectivity testing.
Project Objectives

**Project Objectives**
Create a custom AWS VPC.
Configure public and private subnets across two Availability Zones.
Configure and attach an Internet Gateway.
Create public and private route tables.
Configure routing for internet connectivity.
Implement security groups following the principle of least privilege.
Deploy test EC2 instances.
Perform network connectivity and DNS resolution tests.
Document the architecture and implementation.

**Network Architecture**
**AWS Region**: Europe (Ireland) – eu-west-1
**VPC CID**R: 10.20.0.0/16
The network consists of:
One custom VPC.
Two public subnets.
Two private subnets.
Two Availability Zones.
One Internet Gateway.
Separate public and private route tables.

**Architecture Diagram**

**CIDR and Subnet Configuration**
Subnet                  Type            AZ           CIDR
Public-subnet-1        public      eu-west-1a      10.20.1.0/24
public-subnet-2        public      eu-west-1b      10.20.2.0/24
private-subnet-1       private     eu-west-1a      10.20.3.0/24
private-subnet-2       private     eu-west-1b      10.20.4.0/24

**Routing Configuration**

Public Route Table
Destination       Target
VPC CIDR          LOCAL
0.0.0.0/0         Internet Gateway

This allows internet-bound IPv4 traffic from appropriately configured public resources to reach the Internet Gateway.

Private Route table
Destination        Target
VPC CIDR           LOCAL

Private subnets do not have a direct default route to the Internet Gateway.

**Connectivity Flow**
Public Subnet
internet -> internet Gateway -> Public Route Table -> Public Subnet -> EC2 Instance
Private Subnet
Private EC2 Instance -> Private Route Table -> Internel VPC Network
This private Subnet does not have a direct Internet Access through the Internet Gateway

Security Configuration
Security groups are configured to control network traffic.
The implementation follows the principle of least privilege by allowing only the required traffic.
Administrative access such as SSH should not be exposed to the entire internet.
Actual security group rules will be documented after implementation.

VPC COnfiguration
<img width="960" height="540" alt="Screenshot 2026-11-19 233349" src="https://github.com/user-attachments/assets/6b6505da-08ba-4dc7-ac1b-b62c6e7645c5" />
Subnet Configuration
<img width="960" height="540" alt="Screenshot 2026-11-19 232525" src="https://github.com/user-attachments/assets/2f87a351-2f97-4c24-82b3-6f49fec73ddf" />
Internet Gateway attachment
<img width="960" height="540" alt="Screenshot 2026-11-19 233518" src="https://github.com/user-attachments/assets/c6b9c205-baf6-4654-bbd7-79d8736b3107" />
Public Route Table
<img width="960" height="540" alt="Screenshot 2026-11-19 233618" src="https://github.com/user-attachments/assets/a8919cd9-237d-47f4-b053-a60eae6e43c0" />
Private Routr Table
<img width="960" height="540" alt="Screenshot 2026-11-19 233648" src="https://github.com/user-attachments/assets/7e2f7029-c53f-40c7-bb96-454c733bc782" />
Security Group Configuration
<img width="960" height="540" alt="Screenshot 2026-11-19 233823" src="https://github.com/user-attachments/assets/2fb74b6f-e622-4dd7-b7c6-5bea20098c0a" />
EC2 Deployment
<img width="960" height="540" alt="Screenshot 2026-11-19 233216" src="https://github.com/user-attachments/assets/2c8fb0b4-2d86-4a19-8f66-9d69370a9d9f" />
**Connectivity Testing**
<img width="639" height="301" alt="Screenshot 2026-11-19 231906" src="https://github.com/user-attachments/assets/b334ca0d-3050-41ef-a73b-e37b90254eee" />

**Conclusion**
This project demonstrates the design and practical implementation of a custom AWS network with public and private network segmentation.
It helps develop practical knowledge of cloud networking, routing, security boundaries and connectivity troubleshooting.








