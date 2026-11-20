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
