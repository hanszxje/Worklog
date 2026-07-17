---
title: "Week 9"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

**Weekly objectives:**
- Execute Lab 18 to activate AWS Security Hub for compliance scanning.
- Execute Lab 22 to configure secure IAM roles for AWS Lambda.
- Study database services RDS, Aurora, Redshift, and ElastiCache.
- Execute Lab 28 (Region-based IAM), Lab 30 (Boundaries), and Lab 33 (KMS, CloudTrail).

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Executed Lab 18, enabling AWS Security Hub and configuring standard CIS AWS Foundations benchmarks. | Jun 22 |
| Tuesday | Executed Lab 22, creating a secure Lambda execution role and restricting security group ports. | Jun 23 |
| Wednesday | Studied Database classifications on AWS, comparing relational RDS/Aurora against caching solutions like ElastiCache. | Jun 24 |
| Thursday | Executed Lab 28 and Lab 30, exploring region-restricted IAM policies and Permission Boundaries. | Jun 25 |
| Friday | Executed Lab 33, setting up AWS KMS key encryption on S3 buckets and configuring AWS CloudTrail log trails. | Jun 26 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Obtained overall security score and prioritized list of resource security improvements.
  - Lesson: Security Hub centralizes security alerts from multiple services, providing a single security monitoring dashboard.
- **Tuesday:**
  - Result Achieved: Deployed test Lambda in VPC subnets, restricting access rules targeting internal resources only.
  - Lesson: Lambda execution roles must explicitly define target cloudwatch logging write rules.
- **Wednesday:**
  - Result Achieved: Understood OLTP (transactional databases) vs OLAP (analytical data warehouses like Redshift).
  - Lesson: Primary/Foreign keys enforce relational schemas, while Indexes optimize query response speeds.
- **Thursday:**
  - Result Achieved: Created user policy templates restricting resource deployment to ap-southeast-1 region only.
  - Lesson: Permission boundaries define the maximum privileges an IAM entity can have, preventing privilege escalation.
- **Friday:**
  - Result Achieved: Enabled audit trail logging of all administrative API calls across the AWS account.
  - Lesson: CloudTrail logs are critical for security compliance audits and tracing resource modification history.
