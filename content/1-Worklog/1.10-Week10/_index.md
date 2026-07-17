---
title: "Week 10"
date: 2026-06-28
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

**Weekly objectives:**
- Design overall system runtime architecture for Capstone Project.
- Design Edge Security layer using AWS WAF and CloudFront CDN.
- Design asynchronous ETL pipeline connecting RDS PostgreSQL to S3 Parquet.
- Apply AWS Well-Architected Framework 6 pillars and calculate cost via Pricing Calculator.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Designed the overall system runtime architecture diagram, mapping client traffic to compute servers. | Jun 29 |
| Tuesday | Designed the Edge Security layers, combining Amazon CloudFront CDN with AWS WAF firewall protections. | Jun 30 |
| Wednesday | Designed the asynchronous ETL pipeline architecture, mapping Glue Jobs connecting RDS PostgreSQL to S3. | Jul 01 |
| Thursday | Evaluated the system architecture designs against the 6 pillars of the AWS Well-Architected Framework. | Jul 02 |
| Friday | Estimated monthly running costs of all planned resources using the AWS Pricing Calculator. | Jul 03 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Approved decoupled runtime topology separating backend services from predictive training nodes.
  - Lesson: A decoupled layout prevents heavy machine learning training jobs from impacting frontend web performance.
- **Tuesday:**
  - Result Achieved: Created firewall rules to block SQL injection and Rate Limiting constraints to prevent DDoS attacks.
  - Lesson: Caching static frontend assets in CloudFront Edge locations reduces latency and server load.
- **Wednesday:**
  - Result Achieved: Drafted raw data extraction from business tables and Pyspark lag feature calculation logic.
  - Lesson: Storing feature tables in a separate database allows the model to query ML parameters rapidly.
- **Thursday:**
  - Result Achieved: Optimized security boundaries and reliability setups (multi-AZ databases, automated backups).
  - Lesson: Well-architected reviews ensure systems remain resilient, secure, and cost-efficient.
- **Friday:**
  - Result Achieved: Calculated predicted monthly budget, choosing db.t3.micro and t3.medium resources to stay cost-optimal.
  - Lesson: Calculating budget estimations before deployment avoids unexpected high billing surprises.
