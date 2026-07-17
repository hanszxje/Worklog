---
title: "Week 3"
date: 2026-05-10
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Weekly objectives:**
- Study VPC network routing theory, Internet Gateways, and public vs private subnets.
- Understand NAT Gateway functionalities for private subnet internet routing.
- Configure EC2 Instance Connect Endpoint (EICE) for secure SSH without public IPs.
- Perform hands-on Lab deploying a NAT Gateway and test private subnet connectivity.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Studied Virtual Private Cloud (VPC) core concepts, routing tables, public subnets, and internet gateway attachments. | May 11 |
| Tuesday | Researched NAT Gateways and compared Public vs Private NAT setups. Planned allocation of Elastic IPs. | May 12 |
| Wednesday | Studied EC2 Instance Connect Endpoint (EICE) mechanism. Configured endpoint boundaries in private subnets. | May 13 |
| Thursday | Configured Inbound/Outbound Rules of the VPC Security Groups to authorize EICE traffic. | May 14 |
| Friday | Executed the VPC Lab, deploying a NAT Gateway and EICE endpoint. Audited network routing by running outbound updates. | May 15 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Understood how subnet masking and route targets define public and private subnets.
  - Lesson: Public subnets must contain route rules targeting the Internet Gateway (IGW).
- **Tuesday:**
  - Result Achieved: Learned how NAT Gateways translate source IPs to allow private instances to contact external systems safely.
  - Lesson: NAT Gateways must be placed in a public subnet with a routed path targeting an IGW.
- **Wednesday:**
  - Result Achieved: Created EICE endpoint allowing direct SSH connections through the AWS Console/CLI safely.
  - Lesson: EICE removes the need to maintain public bastion hosts, reducing resource costs and security risks.
- **Thursday:**
  - Result Achieved: Configured rules to allow port 22 access from EICE IP ranges to the EC2 instances.
  - Lesson: Restricting security groups to specific source endpoints ensures network boundary enforcement.
- **Friday:**
  - Result Achieved: Verified successful internet access from private EC2 server. Completed SSH login tests successfully.
  - Lesson: Auditing network routes using curl/ping commands validates correct private-to-public NAT translation.
