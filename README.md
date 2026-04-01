                                                               🌐 AWS VPC Peering Project
📌 Project Overview <br>
This project demonstrates the implementation of VPC Peering in Amazon Web Services (AWS) <br> to enable secure and private communication between two Virtual Private Clouds (VPCs) within the same region. <br> The setup ensures that resources in different VPCs can communicate using private IP addresses without traversing the public internet.

🎯 Objective <br>
The primary objective of this project is to: <br>
1) Understand AWS VPC networking concepts <br>
2) Establish connectivity between two isolated networks <br>
3) Enable secure communication using private IP addressing <br>
4) Configure routing and security for cross-VPC communication <br>

🏗 Architecture:- <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/f5f4ad3154588e00ef143c558f513198220ced58/images/Architectureof%20vpc%20peering.png) <br>
The architecture consists of: <br>
1) Two VPCs with non-overlapping CIDR blocks <br>
2) Public subnets in each VPC <br>
3) Internet Gateways attached to both VPCs <br>
4) Route tables configured for internet and peering traffic <br>
5) A VPC Peering connection between both VPCs <br>
6) EC2 instances deployed in each subnet  <br>

 //NOTE--> i have demostrated vpc in one single region ,  i can also implement in  diffn region across in one account, aslo implement in 2 different accounts// <br>
 ⚙️ Implementation Details <br>
1. VPC Configuration <br>
Created two VPCs: <br>
VPC1: 10.0.0.0/16 <br>
VPC2: 192.168.0.0/16 <br>
*vpc_setup* <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/vpc_setup.png) <br>

2. Internet Connectivity <br>
Attached Internet Gateways to both VPCs <br>
Enabled internet access for public subnets <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/igw_setup.png) <br>
3. Subnet Configuration <br>
Created one public subnet in each VPC: <br>
VPC1: 10.0.1.0/24 <br>
VPC2: 192.168.1.0/24 <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/subnet_setup.png) <br>

4.Route Table Configuration <br>
Configured routes for internet access (0.0.0.0/0 → IGW) <br>
Added routes for VPC Peering: <br>
VPC1 → 20.0.0.0/16 via Peering <br>
VPC2 → 10.0.0.0/16 via Peering <br> 

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/Route_table.png) <br> 

VPC1 → 20.0.0.0/16 via Peering <br>
![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/Route_table_1%20configuration.png) <br> 
VPC1 → 20.0.0.0/16 via Peering <br>
![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/Route_table2_configuration.png) <br>

5.VPC Peering Setup <br>
Established a peering connection between VPC1 and VPC2 <br>
Accepted and activated the connection <br>
![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/vpc_peering_setup.png) <br>

6. EC2 Deployment <br>
Launched EC2 instances in each VPC <br>
Assigned public IPs for access <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/ec2%20instances.png) <br>

7. Security Configuration <br>
Configured Security Groups to allow: <br>
SSH (Port 22) <br>
ICMP (Ping testing) <br>
for instance_1  <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/SG%201%20CONFIGURATION.png) <br>
 
SSH (Port 22) <br>
ICMP (Ping testing) <br>
for instance_2 <br>
![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/SG_2%20CONFIGURATION.png) <br>

8. Connectivity Testing <br>
Verified successful communication using ping between EC2 instances <br>
Confirmed internet access from both VPCs by private ips, <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/SERVER_1%20TESTING.png) <br>

![image alt](https://github.com/kailasadhav126/aws-vpc-peering-project/blob/47bb1c9559c5dfd38e587dffc658916bade881eb/images/SERVER_2%20TESTING.png)  <br>



“I implemented VPC Peering in AWS to connect two VPCs securely. I configured subnets, route tables, and internet gateways, and enabled private communication between EC2 instances using peering. I also ensured proper security group configuration and validated connectivity using ping.”








