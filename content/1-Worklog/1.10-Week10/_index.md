---
title: "Week 10"
date: 2026-06-28
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# Work Log: Overall System Architecture, Edge Security, and FinOps Pricing

> **Week 10 - June 28, 2026:** Detailed weekly progress log.

---

### Objectives & Learnings for the Week

- Designed the overall infrastructure network diagram and data flow (Runtime Architecture) for the Capstone Project: Fashion Retail & ML Forecasting Pipeline.
- Designed the Edge Security layer integrating AWS WAF to block DDoS/Spam, combined with Amazon CloudFront CDN and an Application Load Balancer (ALB).
- Designed the asynchronous ETL data pipeline, connecting the operational database (RDS PostgreSQL OLTP) to extract raw data to S3 Parquet, running Spark feature engineering on AWS Glue, and ingestion into the training database (RDS PostgreSQL OLAP Feature Store).
- Optimized the architecture based on the 6 pillars of the AWS Well-Architected Framework and conducted FinOps cost estimations using the AWS Pricing Calculator.

---

*Reference: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
