---
title: "Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

**Mục tiêu tuần:**
- Tìm hiểu các nhóm Amazon EC2 Instance Types, so sánh chip Intel/AMD với chip Graviton.
- Nghiên cứu các loại lưu trữ khối EBS (gp2, gp3) và bộ nhớ tạm Instance Store.
- Tìm hiểu cấu hình co giãn Auto Scaling và bộ cân bằng tải Load Balancer (ALB/NLB).
- Cấu hình AWS Backup lập lịch sao lưu tự động cho EC2/RDS.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày |
|---|---|---|
| Thứ Hai | Tìm hiểu phân loại máy chủ EC2 (General Purpose, Compute/Memory Optimized) và các kiến trúc vi xử lý đi kèm. | 25/5 |
| Thứ Ba | Nghiên cứu ổ đĩa Elastic Block Store (EBS), so sánh gp2/gp3, IOPS và bộ nhớ tạm Instance Store. | 26/5 |
| Thứ Tư | Tìm hiểu cơ chế co giãn tự động Auto Scaling và định tuyến cân bằng tải Elastic Load Balancing. | 27/5 |
| Thứ Năm | Nghiên cứu giải pháp chia sẻ dữ liệu qua Amazon EFS (Linux NFS) và Amazon FSx (Windows SMB). | 28/5 |
| Thứ Sáu | Thực hành Lab 13, thiết lập kế hoạch sao lưu AWS Backup, cấu hình vòng đời dữ liệu và chạy thử khôi phục. | 29/5 |

**Kết quả đạt được trong tuần là gì:**
- **Thứ Hai:**
  - Kết quả đạt được: So sánh hiệu năng và chi phí của CPU Intel/AMD với dòng chip tiết kiệm điện năng AWS Graviton (ARM).
  - Bài học: Máy chủ chip Graviton giúp tối ưu hóa chi phí đến 40% so với thế hệ chip x86 truyền thống cho cùng hiệu năng.
- **Thứ Ba:**
  - Kết quả đạt được: Nắm vững cách gp3 tách rời cấu hình băng thông khỏi dung lượng ổ đĩa, giúp tiết kiệm chi phí lưu trữ hơn gp2.
  - Bài học: Dữ liệu trên Instance Store sẽ mất khi tắt máy (Ephemeral), chỉ phù hợp làm cache hoặc dữ liệu tạm thời.
- **Thứ Tư:**
  - Kết quả đạt được: Hiểu rõ cơ chế điều hướng gói tin dựa trên đường dẫn (path-based routing) và luật kiểm tra sức khỏe máy chủ.
  - Bài học: ALB hoạt động ở tầng ứng dụng (L7) xử lý HTTP/HTTPS, còn NLB hoạt động ở tầng giao vận (L4) tối ưu cho TCP/UDP.
- **Thứ Năm:**
  - Kết quả đạt được: Chi tiết các thiết lập hệ thống chia sẻ tệp tin của Amazon EFS và Amazon FSx.
  - Bài học: EFS tự động co giãn dung lượng và hiệu năng, thích hợp cho hệ thống container microservices.
- **Thứ Sáu:**
  - Kết quả đạt được: Cấu hình sao lưu định kỳ hàng ngày thành công. Khôi phục máy chủ ảo thử nghiệm từ bản backup chạy ổn định.
  - Bài học: Cấu hình tự động chuyển bản sao lưu cũ sang Archive giúp tối ưu hóa chi phí lưu trữ lâu dài.
