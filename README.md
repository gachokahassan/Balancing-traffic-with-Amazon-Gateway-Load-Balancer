# Scaling Network Traffic with AWS Gateway Load Balancer (GWLB) 🌐🚦

[![AWS](https://img.shields.io/badge/AWS-100000?style=flat&logo=amazon&logoColor=FFFFFF&labelColor=5C5C5C&color=FF7300)](https://aws.amazon.com/)
[![GWLB](https://img.shields.io/badge/AWS_GWLB-100000?style=flat&logo=amazonaws&logoColor=white&labelColor=494949&color=569A31)](https://docs.aws.amazon.com/elasticloadbalancing/)
[![VPC](https://img.shields.io/badge/AWS_VPC-100000?style=flat&logo=amazonaws&logoColor=white&labelColor=494949&color=569A31)](https://docs.aws.amazon.com/vpc/)

---

## 📜 **Table of Contents**

1. [Project Overview](#project-overview)  
2. [Architecture](#architecture)  
3. [Features](#features)  
4. [Key Deliverables](#key-deliverables)  
5. [Challenges and Lessons Learned](#challenges-and-lessons-learned)  
6. [Outcome](#outcome)  
7. [Tools and Technologies Used](#tools-and-technologies-used)  
8. [Steps to Reproduce](#steps-to-reproduce)  
9. [Screenshots](#screenshots)  
10. [Acknowledgments](#acknowledgments)  
11. [Author](#author)  

---

## Project Overview

This project focuses on deploying an AWS Gateway Load Balancer (GWLB) to enhance the performance, scalability, and availability of virtual appliances. By combining a transparent network gateway and a load balancer, GWLB ensures seamless traffic management, dynamic scaling, and efficient routing for high-demand applications. The implementation leverages GWLB’s ability to manage traffic at OSI Layer 7, significantly improving the performance of underlying web servers and ensuring a robust architecture for scalable network solutions.

---

## Architecture (VPC-CIDR)

![GWLB Architecture Diagram](./Images/VPC-CIDR.png)

- **VPC with Transit Gateway**: A centralized hub that routes traffic to various VPCs.  
- **GWLB**: Acts as a single entry/exit point for traffic across multiple virtual appliances.  
- **Elastic Network Interfaces (ENIs)**: Handle traffic between GWLB and appliance instances.  

---

## Features

- **Transparent Appliance Scaling**: Routes traffic without client awareness of underlying appliance changes.  
- **Auto Scaling**: Ensures optimal performance during traffic spikes.  
- **Flow Stickiness**: Maintains consistent routing for specific client sessions.  
- **Health Monitoring**: Removes unhealthy appliances automatically from the target group.  

---

## Key Deliverables

1. **VPC and Subnet Design**:
   - Deployed a custom VPC with subnets for GWLB and appliances.  
   - Configured route tables for proper traffic flow.  

2. **GWLB Setup**:
   - Created GWLB and configured a target group for appliance instances.  
   - Associated GWLB with subnets and VPC endpoints.  

3. **Appliance Instances**:
   - Deployed virtual appliances for packet inspection and routing.  
   - Integrated with GWLB using Elastic Network Interfaces.  

4. **Monitoring and Security**:
   - Enabled logging with AWS CloudWatch for GWLB metrics.  
   - Applied security groups to enforce strict access policies.  

---

## Challenges and Lessons Learned

### Challenges
- Properly configuring flow stickiness to maintain session consistency.  
- Debugging traffic loops caused by misconfigured route tables.  

### Lessons Learned
- Using **AWS Gateway Load Balancer Endpoints (GWLBE)** simplifies appliance integration.  
- Flow stickiness is critical for stateful appliances like firewalls.  

---

## Outcome

The project successfully demonstrated **scalable, fault-tolerant network traffic management** using AWS Gateway Load Balancer. The setup ensures seamless integration with network appliances, efficient traffic distribution, and robust session management.

---

## Tools and Technologies Used

- **AWS VPC**: Networking backbone.  
- **AWS Gateway Load Balancer (GWLB)**: Traffic management and appliance scaling.  
- **Elastic Network Interfaces (ENI)**: Appliance connectivity.  
- **AWS CloudWatch**: Monitoring and logging.  

---

## Steps to Reproduce

1. **Create a VPC**:
   - Define public and private subnets for GWLB and appliances.  
   - Attach an Internet Gateway and configure route tables.  

2. **Deploy Appliance Instances**:
   - Launch instances in the private subnet.  
   - Configure ENIs for traffic forwarding.  

3. **Configure GWLB**:
   - Create GWLB and its target group.  
   - Associate GWLB with appliance ENIs.  

4. **Test Traffic Flow**:
   - Route traffic through GWLB.  
   - Verify performance and appliance scaling.  

---

## Screenshots

### Gateway Load Balancer Console  
![GWLB Console](./Images/gwlb-console.png)  

### Packet Inspection Appliance Logs  
![Appliance Logs](./Images/appliance-logs.png)  

---

## Acknowledgments

Thanks to **AWS Documentation**, **NextWork Community**, and **AWS Learning Center** for resources and insights that guided this project.

---

## Author

**Hassan Gachoka**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/gachokahassan)  
[![Portfolio](https://img.shields.io/badge/Portfolio-Explore-brightgreen)](https://learn.nextwork.org/overwhelmed_cyan_adorable_thunder/portfolio)  

