                                                               🌐 AWS VPC Peering Project
📌 Project Overview
This project demonstrates the implementation of VPC Peering in Amazon Web Services (AWS) to enable secure and private communication between two Virtual Private Clouds (VPCs) within the same region. The setup ensures that resources in different VPCs can communicate using private IP addresses without traversing the public internet.

🎯 Objective
The primary objective of this project is to:
1)Understand AWS VPC networking concepts
2)Establish connectivity between two isolated networks
3)Enable secure communication using private IP addressing
4)Configure routing and security for cross-VPC communication

🏗 Architecture:-

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/f5f4ad3154588e00ef143c558f513198220ced58/images/Architectureof%20vpc%20peering.png)
The architecture consists of:
1)Two VPCs with non-overlapping CIDR blocks
2)Public subnets in each VPC
3)Internet Gateways attached to both VPCs
4)Route tables configured for internet and peering traffic
5)A VPC Peering connection between both VPCs
6)EC2 instances deployed in each subnet

 //NOTE--> i have demostrated vpc in one single region ,  i can also implement in  diffn region across in one account, aslo implement in 2 different accounts//
 ⚙️ Implementation Details
1. VPC Configuration
Created two VPCs:
VPC1: 10.0.0.0/16
VPC2: 192.168.0.0/16









