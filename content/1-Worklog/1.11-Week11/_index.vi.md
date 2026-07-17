---
title: "Tuần 11"
date: 2026-07-05
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

**Mục tiêu tuần:**
- Khởi tạo hạ tầng mạng VPC và cơ sở dữ liệu RDS PostgreSQL (fashion-rds, training-db).
- Tạo S3 buckets lưu trữ mã nguồn frontend và tệp lưu mô hình dự báo XGBoost.
- Cấu hình AWS Glue Python Shell và PySpark ETL Job tính toán đặc trưng.
- Cấu hình máy chủ EC2 chạy script huấn luyện mô hình XGBoost dự báo doanh số.
- Triển khai API dự báo qua AWS Lambda, API Gateway và Cognito User Pool.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Triển khai hạ tầng mạng VPC. Khởi tạo hai cơ sở dữ liệu Amazon RDS PostgreSQL (`fashion-rds` và `training-db`). | 6/7 |
| Thứ Ba | Tạo các S3 bucket lưu trữ mã nguồn trang web tĩnh (frontend) và lưu trữ tệp mô hình ML. | 7/7 |
| Thứ Tư | Viết mã nguồn cho các Glue Jobs: Python Shell (`de-fashion-rds-extract`) và PySpark (`glue_feature_engineering.py`). | 8/7 |
| Thứ Năm | Cấu hình máy chủ EC2 huấn luyện mô hình. Chạy script Python huấn luyện mô hình XGBoost Regressor. | 9/7 |
| Thứ Sáu | Lập trình hàm AWS Lambda xử lý API dự báo, tích hợp API Gateway và bảo mật xác thực bằng Cognito. | 10/7 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Khởi tạo thành công hai database nằm ẩn trong Private Subnet và phân chia Security Group.
  - Bài học: Đặt database trong Private Subnet giúp ngăn ngừa các truy cập quét cổng không hợp lệ từ bên ngoài.
- **Thứ Ba:**
  - Kết quả đạt được: Cấu hình thành công Bucket Policy cho phép truy cập frontend và lưu trữ mô hình học máy.
  - Bài học: Bucket chứa frontend cần phân quyền công khai để duyệt web, trong khi bucket chứa model phải giữ chế độ private.
- **Thứ Tư:**
  - Kết quả đạt được: Tích hợp Driver kết nối PostgreSQL JDBC vào thư viện AWS Glue, cấu hình thông số kết nối.
  - Bài học: Glue Job muốn kết nối RDS PostgreSQL cần khai báo đường dẫn tệp driver `.jar` đặt trên S3.
- **Thứ Năm:**
  - Kết quả đạt được: Mô hình XGBoost được huấn luyện thành công và tự động upload tệp mô hình `.pkl` lên S3.
  - Bài học: Lưu trữ tệp model trên S3 giúp phân tách tải giữa máy chủ huấn luyện và hàm gọi API dự báo.
- **Thứ Sáu:**
  - Kết quả đạt được: Hàm Lambda đọc model từ S3 chạy dự báo và trả về JSON qua API Gateway đã cấu hình xác thực token.
  - Bài học: Mô hình serverless tự động co giãn theo số lượng request giúp tiết kiệm tối đa chi phí vận hành.
