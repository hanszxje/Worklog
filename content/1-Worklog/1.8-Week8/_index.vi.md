---
title: "Tuần 8"
date: 2026-06-14
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Mục tiêu tuần:**
- Tìm hiểu chiến lược khắc phục sự cố Disaster Recovery dựa trên RTO và RPO.
- Phân biệt các mô hình DR: Backup/Restore, Pilot Light, Warm Standby và Multi-Site.
- Thực hành Lab 25 triển khai Amazon FSx for Windows File Server Multi-AZ.
- Tích hợp dịch vụ thư mục Microsoft Active Directory với máy chủ tệp tin.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Nghiên cứu các khái niệm cơ bản về khắc phục sự cố sau thảm họa (DR), đặc biệt là chỉ số RTO và RPO. | 15/6 |
| Thứ Ba | So sánh sơ đồ kiến trúc các giải pháp DR: Backup/Restore, Pilot Light, Warm Standby và Multi-Site. | 16/6 |
| Thứ Tư | Thực hành Lab 25, cấu hình tạo ổ đĩa chia sẻ Amazon FSx for Windows File Server dạng Multi-AZ. | 17/6 |
| Thứ Năm | Cấu hình AWS Directory Service, thiết lập domain Microsoft Active Directory để tích hợp xác thực với FSx. | 18/6 |
| Thứ Sáu | Tìm hiểu tổng quan về dịch vụ bảo mật Amazon Cognito và mã hóa dữ liệu tĩnh thông qua AWS KMS. | 19/6 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Xác định rõ ý nghĩa của RTO (thời gian hệ thống ngừng hoạt động tối đa) và RPO (lượng dữ liệu tối đa chấp nhận mất).
  - Bài học: Muốn giảm tối đa RTO/RPO yêu cầu chạy hệ thống song song (Active-Active), làm tăng chi phí hạ tầng rất nhiều.
- **Thứ Ba:**
  - Kết quả đạt được: Nắm vững ưu nhược điểm: Pilot Light chỉ duy trì database hoạt động liên tục còn máy ảo EC2 ở trạng thái chờ tắt.
  - Bài học: Lựa chọn phương án DR tối ưu phụ thuộc vào ngân sách của doanh nghiệp và mức độ quan trọng của hệ thống.
- **Thứ Tư:**
  - Kết quả đạt được: Khởi tạo thành công hệ thống tệp tin Windows dùng chung, tự động nhân bản dữ liệu qua 2 vùng AZ.
  - Bài học: FSx Multi-AZ tự động chuyển vùng khi có sự cố ở AZ chính, giúp dữ liệu luôn sẵn sàng cho doanh nghiệp.
- **Thứ Năm:**
  - Kết quả đạt được: Tích hợp thành công AD với FSx, cho phép kiểm soát quyền truy cập tệp tin theo tài khoản nhân viên.
  - Bài học: Tích hợp AD giúp đồng bộ hóa tài khoản đăng nhập của nhân viên công ty với các phân quyền thư mục trên cloud.
- **Thứ Sáu:**
  - Kết quả đạt được: Nắm vững lý thuyết Cognito hỗ trợ đăng ký/đăng nhập người dùng và KMS quản lý khóa mã hóa ổ đĩa.
  - Bài học: KMS cung cấp khả năng mã hóa trong suốt cho ổ đĩa, còn Cognito giúp tách biệt quản lý danh tính khỏi mã nguồn ứng dụng.
