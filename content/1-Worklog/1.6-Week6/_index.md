---
title: "Week 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

**Weekly objectives:**
- Research Amazon EC2 Instance Types, comparing Intel, AMD, and AWS Graviton.
- Learn block storage mechanisms of Amazon EBS (gp2, gp3) and Instance Store.
- Study Auto Scaling Groups (ASG) and Elastic Load Balancing (ALB/NLB).
- Configure AWS Backup scheduled policies for EC2/RDS restoration.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Researched Amazon EC2 Instance families (General Purpose, Compute Optimized, Memory Optimized) and chip architectures. | May 25 |
| Tuesday | Studied Elastic Block Store (EBS) volumes (gp2 vs gp3 performance, provisioned IOPS) and transient Instance Store. | May 26 |
| Wednesday | Studied Auto Scaling Groups (ASG) scaling policies and Elastic Load Balancing (ALB/NLB) path-based routing rules. | May 27 |
| Thursday | Researched shared file storage options on AWS, comparing Amazon EFS (Linux NFS) and Amazon FSx (Windows SMB). | May 28 |
| Friday | Executed Lab 13, configuring AWS Backup plans, lifecycle rules (cold storage transition), and ran file restoration tests. | May 29 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Compared Intel/AMD processor performance against custom-built energy-efficient ARM AWS Graviton chips.
  - Lesson: Graviton instances offer up to 40% better price-performance for modern web applications.
- **Tuesday:**
  - Result Achieved: Understood how gp3 volumes decouple throughput from capacity, reducing storage costs compared to gp2.
  - Lesson: Instance Store provides low-latency NVMe speed but is ephemeral; data is lost when instances terminate.
- **Wednesday:**
  - Result Achieved: Understood load-balancer target group mapping and health check validation rules.
  - Lesson: ALB routes HTTP/HTTPS layer 7 requests, whereas NLB is optimized for high-performance TCP layer 4 traffic.
- **Thursday:**
  - Result Achieved: Learned usage scenarios for multiple instances writing to a shared file mount concurrently.
  - Lesson: EFS scales capacity and throughput automatically, making it ideal for container workloads.
- **Friday:**
  - Result Achieved: Configured daily scheduled backups of EC2/RDS, verified successful simulation recovery.
  - Lesson: Automated snapshot lifecycle rules move old backups to cold storage, reducing backup costs.
