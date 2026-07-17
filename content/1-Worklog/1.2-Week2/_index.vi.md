---
title: "Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

**Mục tiêu tuần:**
- Khám phá giao diện AWS Management Console, tìm hiểu cách sử dụng và cấu hình AWS CLI cùng công cụ CloudShell.
- Nghiên cứu chuyên sâu về quản lý bảo mật đám mây, cấu hình xác thực đa yếu tố (MFA/2FA) cho tài khoản Root.
- Tìm hiểu sự khác biệt và giải pháp phân tách quyền hạn sử dụng IAM Policies và IAM Roles.
- Hoàn thành và nắm vững kiến thức lý thuyết Module 02 về hạ tầng toàn cầu của AWS.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Khám phá giao diện tổng thể của AWS Management Console và tìm hiểu cấu trúc hạ tầng toàn cầu của AWS. | 27/4 |
| Thứ Ba | Cài đặt gói AWS CLI lên máy cá nhân, cấu hình thông số kết nối bảo mật và thực hành trên CloudShell. | 28/4 |
| Thứ Tư | Thiết lập xác thực đa yếu tố (MFA/2FA) cho tài khoản Root sử dụng phần mềm Google Authenticator. | 29/4 |
| Thứ Năm | Tìm hiểu lý thuyết về IAM Policies, IAM Roles và cấu trúc viết mã chính sách bảo mật JSON. | 30/4 |
| Thứ Sáu | Tạo tài khoản phụ IAM User cho lập trình viên, đưa vào nhóm admin và kiểm tra phân quyền truy cập. | 1/5 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: Làm quen với thanh tìm kiếm dịch vụ, bộ chọn Region và bố cục trang quản lý. Đã hoàn thành lý thuyết Module 02.
  - Bài học: Các AWS Region chứa nhiều Availability Zone (AZ) cô lập lẫn nhau để phòng chống sự cố diện rộng.
- **Thứ Ba:**
  - Kết quả đạt được: Kết nối thành công máy cá nhân với AWS Cloud thông qua CLI, chạy thử các lệnh truy vấn cơ bản.
  - Bài học: CloudShell cung cấp giao diện terminal tiện lợi trên trình duyệt, tự động thừa hưởng quyền truy cập hiện tại.
- **Thứ Tư:**
  - Kết quả đạt được: Tài khoản root được bảo vệ an toàn bằng mật khẩu và mã OTP. Đã kiểm tra luồng đăng nhập mới.
  - Bài học: Không bao giờ được sử dụng tài khoản root cho các công việc hàng ngày để giảm thiểu rủi ro bảo mật.
- **Thứ Năm:**
  - Kết quả đạt được: Nắm rõ cách thức hoạt động của JSON Policy định nghĩa Action, Resource và Effect.
  - Bài học: Policies gán trực tiếp cho người dùng, trong khi Roles dùng để cấp quyền cho các tài nguyên/máy chủ hoạt động.
- **Thứ Sáu:**
  - Kết quả đạt được: Hạn chế thành công việc dùng tài khoản root bằng việc chuyển sang dùng tài khoản IAM User mới tạo.
  - Bài học: Nguyên tắc phân quyền tối thiểu (Least Privilege) giúp hạn chế tối đa việc lạm quyền và giảm rủi ro rò rỉ thông tin.
