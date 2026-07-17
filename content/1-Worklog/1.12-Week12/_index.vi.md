---
title: "Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

**Mục tiêu tuần:**
- Lập trình giao diện Web Portal tương tác bằng ReactJS và Node.js.
- Triển khai ứng dụng lên máy chủ EC2 Ubuntu, quản lý tiến trình bằng PM2.
- Cấu hình máy chủ reverse proxy Nginx định tuyến cổng 80 vào cổng ứng dụng nội bộ.
- Thiết lập chứng chỉ bảo mật HTTPS SSL thông qua Certbot Let's Encrypt.
- Thực hiện kiểm thử toàn trình End-to-End (E2E Test) trên môi trường Cloud.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Lập trình giao diện Dashboard ReactJS, vẽ biểu đồ Plotly thể hiện kết quả doanh số thực tế và dự báo. | 6/7 |
| Thứ Ba | Khởi tạo máy chủ EC2 Ubuntu. Cloned mã nguồn, cấu hình biến môi trường và chạy nền ứng dụng bằng PM2. | 7/7 |
| Thứ Tư | Cài đặt và cấu hình máy chủ Nginx làm Reverse Proxy định tuyến cuộc gọi cổng 80 về cổng 3000. | 8/7 |
| Thứ Năm | Cấu hình tên miền trỏ về IP máy chủ, chạy Certbot Let's Encrypt cài đặt chứng chỉ bảo mật HTTPS SSL. | 9/7 |
| Thứ Sáu | Kiểm thử toàn trình hệ thống với các vai trò người dùng khác nhau. Hoàn thiện các tài liệu báo cáo thực tập. | 10/7 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Hoàn thành giao diện hiển thị bản đồ cửa hàng và các thông báo cảnh báo nguy cơ thiếu hụt hàng hóa.
  - Bài học: Thiết kế theo giao diện Glassmorphism giúp trang Dashboard trực quan, hiện đại và thu hút người dùng.
- **Thứ Ba:**
  - Kết quả đạt được: Ứng dụng backend Node.js khởi chạy chạy nền ổn định dưới sự giám sát tự khởi động lại của PM2.
  - Bài học: Sử dụng PM2 giúp giám sát và tự động khởi chạy lại ứng dụng Node.js khi gặp sự cố crash.
- **Thứ Tư:**
  - Kết quả đạt được: Định tuyến thành công các request HTTP gửi đến cổng 80 vào cổng 3000 của Node.js.
  - Bài học: Reverse Proxy qua Nginx giúp tăng bảo mật ứng dụng bằng cách ẩn đi cổng chạy thực tế của backend.
- **Thứ Năm:**
  - Kết quả đạt được: Cài đặt chứng chỉ SSL thành công. Nginx tự động chuyển hướng mọi truy cập HTTP sang HTTPS bảo mật.
  - Bài học: HTTPS là giao thức bắt buộc để bảo mật thông tin đăng nhập và token truyền nhận trên đường truyền mạng.
- **Thứ Sáu:**
  - Kết quả đạt được: Hệ thống phân quyền RBAC và API dự báo hoạt động đúng mong đợi. Nộp báo cáo tổng kết thực tập.
  - Bài học: Kiểm thử toàn trình trước khi đóng gói giúp đảm bảo hệ thống vận hành hoàn hảo khi bàn giao thực tế.
