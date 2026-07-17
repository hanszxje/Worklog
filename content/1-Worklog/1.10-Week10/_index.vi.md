---
title: "Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

**Mục tiêu tuần:**
- Thiết kế sơ đồ kiến trúc runtime tổng thể cho dự án Capstone Fashion Retail.
- Thiết kế lớp bảo mật Edge Security sử dụng AWS WAF và CloudFront CDN.
- Thiết kế luồng dữ liệu ETL bất đồng bộ kết nối RDS PostgreSQL sang S3 Parquet.
- Tối ưu kiến trúc dựa trên 6 trụ cột của AWS Well-Architected Framework và tính chi phí.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Vẽ sơ đồ kiến trúc vận hành tổng thể hệ thống, phân chia luồng đi của người dùng đến máy chủ web. | 22/6 |
| Thứ Ba | Thiết kế lớp bảo mật vòng ngoài, kết hợp phân phối nội dung qua CloudFront và tường lửa AWS WAF. | 23/6 |
| Thứ Tư | Thiết kế luồng xử lý ETL bất đồng bộ, sử dụng AWS Glue trích xuất dữ liệu từ RDS PostgreSQL sang S3. | 24/6 |
| Thứ Năm | Đánh giá và tối ưu hóa kiến trúc hạ tầng dựa trên 6 trụ cột của AWS Well-Architected Framework. | 25/6 |
| Thứ Sáu | Tính toán và tối ưu hóa chi phí sử dụng hạ tầng AWS bằng công cụ AWS Pricing Calculator. | 26/6 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Hoàn thiện bản vẽ kiến trúc phân rã (Decoupled), tách biệt máy chủ web chạy React với máy chủ ML.
  - Bài học: Tách biệt ứng dụng giúp đảm bảo tiến trình huấn luyện AI nặng không làm ảnh hưởng trải nghiệm mua hàng.
- **Thứ Ba:**
  - Kết quả đạt được: Lập cấu hình tường lửa chặn SQL injection và chặn spam request (Rate Limit) phòng ngừa tấn công từ chối dịch vụ.
  - Bài học: Lưu cache nội dung web tĩnh tại các Edge Location của CloudFront giúp giảm tải máy chủ và tăng tốc độ tải trang.
- **Thứ Tư:**
  - Kết quả đạt được: Phác thảo xong luồng trích xuất dữ liệu thô và các bước biến đổi Spark tính đặc trưng chuỗi thời gian.
  - Bài học: Lưu trữ bảng đặc trưng (features) riêng giúp mô hình máy học dễ dàng truy cập mà không ảnh hưởng CSDL nghiệp vụ.
- **Thứ Năm:**
  - Kết quả đạt được: Tăng cường tính tin cậy qua cấu hình DB Multi-AZ, tự động backup và mã hóa dữ liệu.
  - Bài học: Đánh giá Well-Architected giúp phát hiện sớm các lỗ hổng bảo mật và các điểm lãng phí chi phí.
- **Thứ Sáu:**
  - Kết quả đạt được: Ước lượng hóa đơn hàng tháng của dự án, chọn đúng cấu hình máy chủ vừa phải để tiết kiệm ngân sách.
  - Bài học: Tính toán chi phí trước khi triển khai thực tế giúp kiểm soát tài chính tốt và tối ưu hóa hiệu quả đầu tư.
