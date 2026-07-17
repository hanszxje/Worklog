---
title: "Tuần 9"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

**Mục tiêu tuần:**
- Thực hành Lab 18 kích hoạt AWS Security Hub để quét lỗi bảo mật.
- Thực hành Lab 22 cấu hình an toàn Security Group và IAM Role cho AWS Lambda.
- Tìm hiểu Module 06 Database bao gồm RDS, Aurora, Redshift và ElastiCache.
- Thực hành Lab 28 (IAM theo vùng), Lab 30 (Boundaries) và Lab 33 (KMS & CloudTrail).

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Thực hành Lab 18, kích hoạt AWS Security Hub và cấu hình bộ quét bảo mật theo tiêu chuẩn CIS AWS Foundations. | 21/6 |
| Thứ Ba | Thực hành Lab 22, cấu hình IAM Role thực thi và phân vùng Security Group an toàn cho hàm Lambda. | 21/6 |
| Thứ Tư | Học Module 06 về Database. So sánh CSDL quan hệ RDS/Aurora với giải pháp lưu trữ cache ElastiCache. | 21/6 |
| Thứ Năm | Thực hành Lab 28 và Lab 30, tìm hiểu phân quyền IAM theo Region và giới hạn quyền hạn Permission Boundaries. | 21/6 |
| Thứ Sáu | Thực hành Lab 33, cấu hình mã hóa KMS cho S3 bucket và thiết lập CloudTrail ghi nhật ký cuộc gọi API. | 21/6 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Nhận báo cáo điểm số bảo mật và danh sách các lỗi cấu hình tài nguyên cần khắc phục gấp.
  - Bài học: Security Hub thu thập thông tin bảo mật từ nhiều dịch vụ khác nhau giúp quản trị viên dễ dàng theo dõi.
- **Thứ Ba:**
  - Kết quả đạt được: Triển khai thành công Lambda chạy trong VPC, giới hạn chỉ kết nối đến các tài nguyên nội bộ được chỉ định.
  - Bài học: Hàm Lambda cần được cấp quyền ghi log vào CloudWatch Logs để tiện lợi cho việc debug sau này.
- **Thứ Tư:**
  - Kết quả đạt được: Phân biệt rõ CSDL giao dịch trực tuyến OLTP (RDS) và kho dữ liệu phân tích OLAP (Redshift).
  - Bài học: Khóa chính/khóa ngoại giúp đảm bảo tính toàn vẹn dữ liệu, trong khi Index giúp tăng tốc độ truy vấn.
- **Thứ Năm:**
  - Kết quả đạt được: Tạo chính sách bảo mật giới hạn lập trình viên chỉ được phép khởi tạo tài nguyên tại khu vực Singapore.
  - Bài học: Permission Boundaries đặt ra giới hạn trần quyền hạn, ngăn chặn tài khoản con tự ý nâng quyền của mình.
- **Thứ Sáu:**
  - Kết quả đạt được: Bật thành công CloudTrail ghi log mọi hành động tạo/xóa tài nguyên của các user trên tài khoản AWS.
  - Bài học: CloudTrail là công cụ bắt buộc phải bật để truy vết nguồn gốc sự cố rò rỉ hoặc cấu hình sai tài nguyên.
