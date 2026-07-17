---
title: "Tuần 5"
date: 2026-05-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Mục tiêu tuần:**
- Nghiên cứu cơ chế phân giải Hybrid DNS, Route 53 Resolver Endpoints và Resolver Rules.
- Tìm hiểu lý thuyết VPC Peering và kiến trúc liên kết mạng AWS Transit Gateway.
- Thực hành Lab 10 thiết lập Hybrid DNS với Amazon Route 53.
- Thực hành Lab 19 cấu hình VPC Peering và Lab 20 cấu hình AWS Transit Gateway.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Nghiên cứu cơ chế phân giải tên miền Hybrid DNS và vai trò của cổng Route 53 Resolver Inbound/Outbound. | 24/5 |
| Thứ Ba | Tìm hiểu lý thuyết liên thông mạng VPC Peering và giải pháp quản lý tập trung qua AWS Transit Gateway. | 24/5 |
| Thứ Tư | Thực hành Lab 10, thiết lập các Route 53 Resolver Endpoints và cấu hình Rule điều hướng DNS. | 24/5 |
| Thứ Năm | Thực hành Lab 19, thiết lập liên kết VPC Peering kết nối hai VPC. Cấu hình bảng định tuyến Route Table. | 24/5 |
| Thứ Sáu | Thực hành Lab 20, khởi tạo một AWS Transit Gateway và liên kết (Attachment) các mạng VPC con. | 24/5 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Nắm vững nguyên lý điều hướng truy vấn DNS giữa hạ tầng on-premises và AWS Private Hosted Zone.
  - Bài học: Inbound endpoint xử lý truy vấn từ on-prem gửi lên, còn Outbound endpoint chuyển tiếp truy vấn từ AWS xuống dưới.
- **Thứ Ba:**
  - Kết quả đạt được: Hiểu rõ vai trò điều phối mạng của Transit Gateway, giúp giảm độ phức tạp khi kết nối nhiều VPC với nhau.
  - Bài học: Transit Gateway là giải pháp tối ưu cho doanh nghiệp có nhiều tài khoản AWS và mạng VPC cần quản lý tập trung.
- **Thứ Tư:**
  - Kết quả đạt được: Phân giải tên miền thành công hai chiều giữa AWS Hosted Zone và máy ảo đại diện cho hạ tầng on-premises.
  - Bài học: Resolver Rules cho phép định hướng truy vấn thông minh dựa trên hậu tố tên miền mong muốn.
- **Thứ Năm:**
  - Kết quả đạt được: Kiểm thử truyền nhận gói tin trực tiếp qua IP giữa hai máy chủ EC2 thuộc hai VPC khác nhau thành công.
  - Bài học: VPC Peering không hỗ trợ định tuyến bắc cầu (Transitive Routing), yêu cầu kết nối trực tiếp giữa hai VPC.
- **Thứ Sáu:**
  - Kết quả đạt được: Triển khai định tuyến mạng theo mô hình Hub-and-Spoke thành công, quản lý tập trung luồng đi của gói tin.
  - Bài học: Transit Gateway thay thế nhiều liên kết peer nhỏ lẻ bằng một router trung tâm, giúp đơn giản hóa quản trị hệ thống.
