---
title: "Tuần 11"
date: 2026-07-05
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# Nhật ký công việc: Triển khai RDS Database, AWS Glue Spark ETL & Huấn luyện XGBoost

> **Tuần 11 - 05/07/2026:** Báo cáo tiến độ chi tiết hàng tuần.

---

### Các hoạt động và kiến thức tích lũy trong tuần

- Triển khai thực tế hạ tầng mạng VPC và hai cơ sở dữ liệu Amazon RDS PostgreSQL (fashion-rds và training-db) hoạt động độc lập để đảm bảo hiệu suất.
- Thiết lập S3 bucket chứa frontend và S3 bucket chứa tệp mô hình học máy.
- Cấu hình AWS Glue Python Shell job (de-fashion-rds-extract) trích xuất dữ liệu thô và AWS Glue PySpark job (glue_feature_engineering.py) chạy tính toán song song đặc trưng chuỗi thời gian (lags, rolling averages, sales velocity).
- Cấu hình máy chủ huấn luyện EC2 chạy nền Python script huấn luyện mô hình XGBoost Regressor dự báo doanh thu và tự động upload tệp mô hình sales_forecast_model_v1.pkl lên S3 Bucket.
- Triển khai AWS Lambda Forecast API và kết nối định tuyến API Gateway tích hợp Cognito User Pool (JWT), cấu hình AWS WAF bảo vệ API.

---

*Tham khảo: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
