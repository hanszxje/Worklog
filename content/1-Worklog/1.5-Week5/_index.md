---
title: "Week 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Weekly objectives:**
- Study Hybrid DNS resolution, Route 53 Resolver Endpoints, and Resolver Rules.
- Learn about VPC Peering topology and Transit Gateway hub-and-spoke networks.
- Set up Hybrid DNS with Amazon Route 53.
- Configure VPC Peering and AWS Transit Gateway to manage multi-VPC routing.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Studied Hybrid DNS resolution mechanisms and Route 53 Resolver Outbound/Inbound Endpoints. | May 18 |
| Tuesday | Studied VPC Peering and Transit Gateway theories, comparing configuration limits and network scalability. | May 19 |
| Wednesday | Executed Lab 10, configuring Route 53 Resolver Endpoints and forwarding rules. | May 20 |
| Thursday | Executed Lab 19, establishing a VPC Peering connection between two private subnets. Updated route tables. | May 21 |
| Friday | Executed Lab 20, deploying an AWS Transit Gateway and attaching multiple VPC network subnets. | May 22 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Understood how DNS requests query between on-premises domains and AWS private hosted zones.
  - Lesson: Inbound endpoints resolve AWS DNS from on-prem, while Outbound endpoints query on-prem DNS from AWS.
- **Tuesday:**
  - Result Achieved: Learned how Transit Gateway acts as a cloud router, avoiding complex full-mesh peering connections.
  - Lesson: Transit Gateway simplifies networking for multi-account environments, offering centralized firewall controls.
- **Wednesday:**
  - Result Achieved: Successfully resolved names between AWS private domains and test on-premises domain instances.
  - Lesson: Route 53 Resolver Rules allow conditional forwarding based on domain name prefixes.
- **Thursday:**
  - Result Achieved: Verified direct IP communication between EC2 instances in different VPCs.
  - Lesson: VPC Peering does not support transitive routing; connection must be directly established between target VPCs.
- **Friday:**
  - Result Achieved: Successfully routed traffic using a Hub-and-Spoke model, simplifying multi-VPC communications.
  - Lesson: Transit Gateway simplifies route management by replacing multiple point-to-point peerings with a central hub.
