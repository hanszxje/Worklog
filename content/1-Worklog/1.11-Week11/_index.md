---
title: "Week 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

**Weekly objectives:**
- Deploy VPC network structure and provision RDS databases (fashion-rds, training-db).
- Create S3 buckets for frontend web assets and ML model storage.
- Configure AWS Glue Python Shell raw extraction job and PySpark ETL job.
- Configure ML training EC2 server and train XGBoost forecasting model.
- Deploy serverless forecast API via Lambda, API Gateway, and Cognito.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Launched the VPC network infrastructure. Provisioned the target RDS instances (`fashion-rds` and `training-db`). | Jun 29 |
| Tuesday | Created target Amazon S3 buckets for static web asset hosting and ML model repository structures. | Jun 30 |
| Wednesday | Coded the AWS Glue jobs: Python Shell job (`de-fashion-rds-extract`) and PySpark Spark job (`glue_feature_engineering.py`). | Jul 01 |
| Thursday | Configured the machine learning training EC2 server. Executed the training script to train the XGBoost Regressor model. | Jul 02 |
| Friday | Programmed the AWS Lambda forecast API, integrated with API Gateway REST endpoints and Cognito JWT authorization. | Jul 03 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Databases online and isolated inside private subnet groups with security boundaries configured.
  - Lesson: Placing databases inside private subnet groups protects records from external scanning threats.
- **Tuesday:**
  - Result Achieved: Bucket access policies configured. S3 static web hosting configuration established.
  - Lesson: Exposing frontend resources requires configuring public read access policies while keeping model buckets private.
- **Wednesday:**
  - Result Achieved: Configured database connection profiles and jar dependency libraries (PostgreSQL JDBC).
  - Lesson: AWS Glue requires JDBC drivers uploaded to S3 to connect and extract database tables.
- **Thursday:**
  - Result Achieved: Model successfully fitted on lag sales features. Automatically exported `sales_forecast_model_v1.pkl` to S3.
  - Lesson: Storing ML parameters in S3 isolates training workloads from runtime prediction functions.
- **Friday:**
  - Result Achieved: Successfully queried forecasts from public API endpoints secured with token parameters.
  - Lesson: Serverless APIs scale automatically with request volumes, reducing running costs to $0 during inactive hours.
