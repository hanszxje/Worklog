---
title: "Tuần 3"
date: 2026-05-10
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Mục tiêu tuần:**
- Nghiên cứu lý thuyết mạng ảo VPC (Virtual Private Cloud), cơ chế định tuyến qua Route Table, phân biệt IGW, Public/Private Subnets.
- Tìm hiểu về cơ chế hoạt động của NAT Gateway hỗ trợ kết nối Internet từ Private Subnets.
- Cấu hình kết nối an toàn EC2 Instance Connect Endpoint (EICE) để truy cập SSH vào Private Subnets.
- Thực hành Lab triển khai NAT Gateway và EICE, kiểm thử kết nối Internet thành công từ Private Subnets.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Nghiên cứu lý thuyết mạng ảo VPC, cơ chế định tuyến qua Route Table và vai trò của cổng Internet Gateway. | 10/5 |
| Thứ Ba | Tìm hiểu cơ chế NAT Gateway, so sánh giải pháp Public/Private NAT và thiết lập IP tĩnh Elastic IP đi kèm. | 10/5 |
| Thứ Tư | Tìm hiểu giải pháp EC2 Instance Connect Endpoint (EICE). Khởi tạo endpoint kết nối trong Private Subnet. | 10/5 |
| Thứ Năm | Cấu hình quy tắc Inbound/Outbound Rules cho Security Group nhằm cấp quyền kết nối thông qua EICE. | 10/5 |
| Thứ Sáu | Thực hành Lab cấu hình NAT Gateway và EICE. Chạy thử nghiệm kiểm tra cập nhật hệ điều hành từ Private Subnet. | 10/5 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Nắm vững cách thức phân loại Public Subnet và Private Subnet dựa trên bảng định tuyến Route Table.
  - Bài học: Public Subnet bắt buộc phải có quy tắc định tuyến trỏ đến cổng Internet Gateway (IGW) để ra ngoài Internet.
- **Thứ Ba:**
  - Kết quả đạt được: Hiểu rõ cơ chế NAT Gateway giúp máy chủ trong Private Subnet gọi ra ngoài Internet mà không bị bên ngoài tự ý kết nối vào.
  - Bài học: NAT Gateway phải luôn được đặt trong Public Subnet để có thể trung chuyển gói tin ra ngoài.
- **Thứ Tư:**
  - Kết quả đạt được: Tạo thành công EICE endpoint cho phép thực hiện phiên kết nối SSH trực tiếp từ console hoặc máy cá nhân.
  - Bài học: EICE giúp loại bỏ hoàn toàn việc duy trì máy chủ trung chuyển (Bastion Host), giảm chi phí và rủi ro bảo mật.
- **Thứ Năm:**
  - Kết quả đạt được: Thiết lập thành công quy tắc chỉ cho phép kết nối cổng 22 từ dải IP của EICE đến máy chủ EC2.
  - Bài học: Giới hạn nguồn truy cập Security Group theo dải IP nguồn của endpoint giúp tăng độ bảo mật hạ tầng mạng.
- **Thứ Sáu:**
  - Kết quả đạt được: Xác nhận kết nối Internet thành công từ Private Subnet. Phiên kết nối SSH qua EICE hoạt động ổn định.
  - Bài học: Sử dụng các câu lệnh curl/ping giúp nhanh chóng kiểm tra độ chính xác của bảng định tuyến và NAT Gateway.
