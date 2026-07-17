---
title: "Week 11"
date: 2026-07-05
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# Work Log: VPC Database Setup, AWS Glue ETL Pipeline, and XGBoost Model Training

> **Week 11 - July 05, 2026:** Detailed weekly progress log.

---

### Objectives & Learnings for the Week

- Deployed the VPC network infrastructure and two independent Amazon RDS PostgreSQL databases (fashion-rds and training-db) to guarantee performance isolation.
- Set up the S3 bucket for frontend hosting and the S3 bucket for ML model artifacts.
- Configured the AWS Glue Python Shell job (de-fashion-rds-extract) for raw data extraction and the AWS Glue PySpark job (glue_feature_engineering.py) for parallel time-series feature engineering (lags, rolling averages, sales velocity).
- Configured the EC2 training server to run the Python training script in the background, fitting the XGBoost Regressor model and automatically uploading the sales_forecast_model_v1.pkl to the S3 Bucket.
- Deployed the AWS Lambda Forecast API and routed via API Gateway integrated with a Cognito User Pool (JWT), configuring AWS WAF for API protection.

---

*Reference: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
