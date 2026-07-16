---
title: "Tuần 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# Nhật Ký Làm Việc: Quản Lý Chi Phí Chuyên Sâu, Thiết Lập Hệ Thống Cảnh Báo Tự Động và Kiến Thức Hạ Tầng Nền Tảng

> **Tuần 2 - Thứ Hai, ngày 08/06/2026:** Hoàn thành thiết lập cơ chế giám sát chi phí đa lớp, xây dựng quy trình dọn dẹp khẩn cấp khi phát sinh sự cố tài chính, đồng thời tìm hiểu sâu lý thuyết về hạ tầng toàn cầu và bảo mật đám mây trên AWS.

---

### Mục tiêu học tập trong tuần

- Triển khai **Hệ thống cảnh báo chi phí nhiều lớp** để bảo vệ tài khoản một cách tối đa.
- Kích hoạt tính năng **Cost Anomaly Detection** cùng với việc chuẩn hóa quy định gắn tag tài nguyên.
- Lập tài liệu **Cẩm nang xử lý chi tiêu khẩn cấp** thông qua các câu lệnh AWS CLI để tìm và tắt tài nguyên rác.
- Nghiên cứu các chủ đề lý thuyết nền tảng của AWS: Mô hình trách nhiệm chung, IAM, các mô hình dịch vụ lưu trữ, tính toán và hạ tầng vật lý toàn cầu.

---

### Thiết Lập Hệ Thống Cảnh Báo & Giám Sát Chi Phí

#### 1. Cấu hình 3 bộ quy tắc ngân sách qua AWS Budgets

Để theo dõi sát sao lượng tín dụng tiêu dùng và ngăn ngừa rủi ro vượt hạn mức, tôi đã cài đặt 3 bộ quy tắc ngân sách riêng biệt:

| Tên bộ cảnh báo ngân sách | Hạn mức cấu hình | Điều kiện gửi email thông báo |
|---|---|---|
| **Monthly Cap Budget** | $40.00 / tháng | Thông báo khi mức dùng thực tế chạm **80% ($32.00)** |
| **Warning Budget** | $20.00 / tháng | Thông báo khi mức dùng thực tế chạm **50% ($10.00)** |
| **Daily Safeguard Budget** | $5.00 / ngày | Thông báo khi mức dùng thực tế chạm **100% ($5.00)** |

Bộ ngân sách hằng ngày là lớp bảo vệ tức thời, giúp sớm nhận diện các tài nguyên bị cấu hình sai hoặc quên tắt chỉ trong vòng 24h, không để chi phí tích lũy âm thầm đến cuối tháng.

#### 2. Cảnh báo vượt chi tiêu với CloudWatch Billing Alarms

Tôi sử dụng dịch vụ Amazon SNS để phân phối các cảnh báo chi phí (Billing Alarms) từ CloudWatch đến các kênh thông tin tương ứng theo cấp độ nghiêm trọng:

| Ngưỡng ngân sách | Kênh tiếp nhận cảnh báo | Hành động xử lý đề xuất |
|---|---|---|
| **$15.00** | Email cá nhân | Mức độ Thấp; rà soát lại danh sách dịch vụ đang vận hành. |
| **$35.00** | Email + SMS điện thoại | Mức độ Trung bình; kiểm tra kỹ xem có tài nguyên nào chạy sai quy trình. |
| **$60.00** | Email + SMS + Webhook Discord | Mức độ Khẩn cấp; kích hoạt ngay quy trình tắt và dọn dẹp tài nguyên. |

#### 3. Phát hiện chi tiêu bất thường với AWS Cost Anomaly Detection

Kích hoạt công cụ **AWS Cost Anomaly Detection** tích hợp trí tuệ nhân tạo (Machine Learning) để phân tích hành vi chi tiêu và gửi cảnh báo khi phát hiện các biến động chi phí bất thường:
- Đối tượng theo dõi: Tất cả các dịch vụ đang chạy trên tài khoản AWS.
- Ngưỡng kích hoạt cảnh báo: Biến động chi phí vượt quá $5.00 trong một ngày.
- Ưu điểm: Gửi email cảnh báo tức thời ngay khi phát hiện chi tiêu tăng vọt một cách bất thường, không phụ thuộc vào các mốc ngân sách tĩnh đã thiết lập.

---

### Quản Lý Thẻ Tag Tài Nguyên & Bảng Giám Sát Chi Phí

#### Chính sách phân bổ thẻ tag (Resource Tagging)

Nhằm mục đích dễ dàng phân loại chi phí trong AWS Cost Explorer, tất cả các tài nguyên khởi tạo đều bắt buộc tuân thủ quy tắc gắn tag như sau:

| Khóa thẻ (Tag Key) | Ví dụ giá trị (Value) | Vai trò phân loại |
|---|---|---|
| `Project` | `cloud-training` | Chỉ định tài nguyên thuộc dự án huấn luyện nào. |
| `Environment` | `dev` / `testing` | Phân biệt môi trường phát triển thử nghiệm với môi trường test. |
| `Author` | `intern-dev` | Xác định người chịu trách nhiệm quản lý tài nguyên. |

#### Bảng điều khiển CloudWatch Dashboard tập trung

- Thiết lập một bảng điều khiển **CloudWatch Dashboard** trực quan hiển thị đồng thời các biểu đồ theo dõi hiệu năng CPU của EC2 và dự báo tổng chi tiêu ước tính của tháng.
- Theo dõi các chỉ số vận hành để phát hiện sớm các lỗi lặp vô hạn trong các đoạn mã chạy thử, tránh lãng phí tài nguyên đám mây.

---

### Quy Trình Dọn Dẹp Khẩn Cấp & Cẩm Nang CLI

#### 1. Các lệnh quét tài nguyên nhanh qua AWS CLI

Khi hệ thống gửi cảnh báo chi tiêu vượt ngưỡng, sử dụng ngay các dòng lệnh sau trên giao diện terminal để xác định nhanh những dịch vụ đang tiêu hao nhiều chi phí:

```bash
# 1. Liệt kê các instance EC2 đang ở trạng thái Running ở vùng hiện tại
aws ec2 describe-instances --filters "Name=instance-state-name,Values=running" \
  --query 'Reservations[].Instances[].{ID:InstanceId,Type:InstanceType,Zone:Placement.AvailabilityZone}' \
  --output table

# 2. Hiển thị danh sách toàn bộ các DB instance RDS đang hoạt động
aws rds describe-db-instances \
  --query 'DBInstances[].{DBIdentifier:DBInstanceIdentifier,Engine:Engine,Status:DBInstanceStatus}' \
  --output table

# 3. Tìm kiếm các ổ cứng EBS đang rảnh rỗi (vẫn phát sinh phí lưu trữ dù máy chủ ảo đã tắt)
aws ec2 describe-volumes --filters "Name=status,Values=available" \
  --query 'Volumes[].{VolumeID:VolumeId,Size:Size,Zone:AvailabilityZone}' \
  --output table

# 4. Truy vấn các IP tĩnh (Elastic IP) chưa được liên kết với máy ảo nào (gây tốn phí duy trì)
aws ec2 describe-addresses \
  --query 'Addresses[?AssociationId==null].{IP:PublicIp,AllocationId:AllocationId}' \
  --output table
```

#### 2. Kịch bản xử lý sự cố chi phí khẩn cấp
1. Tiến hành đăng nhập nhanh vào AWS Console.
2. Tắt (Stop) hoặc xóa vĩnh viễn (Terminate) các máy chủ `EC2` dư thừa và hủy bỏ các DB instance hoặc cluster `RDS` không cần thiết.
3. Tiến hành xóa bỏ các ổ cứng `EBS` đang trống (trạng thái `available`) và thu hồi (Release) các địa chỉ `Elastic IP` đang rảnh rỗi.
4. Ngắt kết nối với các mô hình thử nghiệm AI trên Bedrock và thu hồi các URL chức năng Lambda không còn sử dụng.

---

### Lý Thuyết Nền Tảng Về Điện Toán Đám Mây

#### Các đặc trưng dịch vụ và mô hình đám mây
- **Elasticity (Tính co giãn):** Khả năng nâng cấp hoặc hạ cấp tài nguyên máy chủ tự động để thích ứng với lượng truy cập thay đổi.
- **Tối ưu tài chính:** Chuyển đổi mô hình đầu tư thiết bị phần cứng ban đầu (CapEx) sang mô hình chi trả chi phí vận hành thực tế theo nhu cầu sử dụng (OpEx).
- **Phạm vi toàn cầu:** Khả năng triển khai ứng dụng tới nhiều khu vực trên thế giới với độ trễ tối thiểu.

| Mô hình điện toán đám mây | Ví dụ cụ thể trên AWS | Trách nhiệm của khách hàng |
|---|---|---|
| **IaaS (Hạ tầng như một dịch vụ)** | Amazon EC2, VPC | Quản trị hệ điều hành, cấu hình mạng, thiết lập runtime cài đặt phần mềm và viết code. |
| **PaaS (Nền tảng như một dịch vụ)** | AWS Elastic Beanstalk, RDS | Chỉ cần quản lý mã nguồn ứng dụng và thiết kế cấu trúc dữ liệu. |
| **SaaS (Phần mềm như một dịch vụ)** | Amazon WorkMail, Chime | Sử dụng dịch vụ trực tiếp thông qua trình duyệt hoặc client; không cần quản lý kỹ thuật. |

#### Hệ thống hạ tầng toàn cầu của AWS
- **Regions (Vùng địa lý):** Các khu vực địa lý tách biệt chứa nhiều trung tâm dữ liệu. Dữ liệu sẽ nằm cố định tại Region được chọn trừ khi được cấu hình sao chép thủ công.
- **Availability Zones (AZs):** Các nhóm trung tâm dữ liệu độc lập về nguồn điện và hạ tầng mạng trong cùng một Region, kết nối thông qua mạng cáp quang siêu tốc. Việc chạy đa ứng dụng trên nhiều AZ giúp đạt tính **Sẵn sàng cao (High Availability)**.
- **Edge Locations (Điểm biên):** Trạm đặt máy chủ cache thuộc mạng lưới CDN (Amazon CloudFront) hỗ trợ phân phối dữ liệu tĩnh đến người dùng ở gần nhất, giúp giảm đáng kể thời gian tải trang.

---

### Cơ Chế Bảo Mật & Quản Trị Hệ Thống (IAM)

- **Mô hình trách nhiệm chung (Shared Responsibility Model):**
  - **Trách nhiệm của AWS (Bảo mật của đám mây - OF the cloud):** Đảm bảo an toàn cho cơ sở hạ tầng vật lý của các Datacenter, máy chủ vật lý, phần mềm ảo hóa và hạ tầng mạng toàn cầu.
  - **Trách nhiệm của khách hàng (Bảo mật trong đám mây - IN the cloud):** Quản trị hệ điều hành, cấu hình các port kết nối (Security Group), phân quyền tài khoản người dùng và thực hiện mã hóa dữ liệu.
- **Các nguyên tắc cốt lõi trong AWS IAM:**
  - **Bảo vệ tài khoản gốc (Root Account):** Bắt buộc bật xác thực đa nhân tố (MFA) và hạn chế tối đa việc sử dụng tài khoản Root cho các hoạt động hằng ngày.
  - **Nguyên lý phân quyền tối thiểu (Least Privilege):** Chỉ cấp phát đúng những quyền hạn cần thiết vừa đủ để hoàn thành tác vụ.
  - **Quản lý theo Nhóm (Groups):** Gán quyền hạn thông qua các Group thay vì gán trực tiếp cho từng cá nhân để quản trị hiệu quả hơn.
  - **Sử dụng chính sách định dạng JSON:** Thiết lập chi tiết các hành động được phép hoặc bị cấm thông qua cấu trúc file JSON gồm Actions, Resources và Conditions.

---

### Tổng Quan Dịch Vụ Lưu Trữ & Cơ Sở Dữ Liệu

- **Amazon S3 (Simple Storage Service):**
  - Hệ thống lưu trữ đối tượng bền vững với cam kết độ an toàn dữ liệu lên tới **99.999999999% (11 số 9)**.
  - Cho phép tự động chuyển đổi các lớp lưu trữ (S3 Standard, Standard-IA, Glacier) để giảm chi phí dựa trên tần suất truy cập dữ liệu.
- **Amazon RDS:** Cơ sở dữ liệu quan hệ được AWS quản trị hoàn toàn, tự động hóa các tác vụ sao lưu, vá lỗi phần mềm và duy trì tính ổn định.
- **AWS Lambda:** Mô hình serverless thực thi mã nguồn khi có sự kiện kích hoạt, có khả năng tự động co giãn và tiết kiệm chi phí tối đa.

---

### Tiến Độ Học Tập Đã Hoàn Thành

| Thời gian học | Chủ đề học tập tập trung | Các dịch vụ AWS liên quan |
|---|---|---|
| **08/06/2026** | Hạ tầng máy chủ ảo và quản lý Instance | Amazon EC2, AMI, Instance Types |
| **08/06/2026** | Quản lý danh tính và phân quyền truy cập | AWS IAM, Roles, Policies |
| **08/06/2026** | Môi trường phát triển và lập trình đám mây | AWS Cloud9, Instance Profiles |
| **08/06/2026** | Lưu trữ dữ liệu và cấu hình lưu trữ tĩnh | Amazon S3, S3 Bucket Policies |
| **08/06/2026** | Thiết lập và quản lý hệ cơ sở dữ liệu | Amazon RDS, DB Engines |

---

### Đúc kết kinh nghiệm sau Tuần 2

1. **Phòng vệ chi phí từ sớm:** Kết hợp hài hòa giữa việc cảnh báo tĩnh (Budgets), thông báo biến động CloudWatch Alarms và phát hiện tự động bằng AI (Cost Anomaly Detection) sẽ bảo vệ tối đa tài khoản khỏi các sự cố phát sinh hóa đơn lớn.
2. **Kỷ luật gắn tag tài nguyên:** Việc gắn thẻ tag đầy đủ là bắt buộc để dễ dàng theo dõi và hạch toán chi phí sử dụng dịch vụ đám mây.
3. **Phản xạ xử lý sự cố:** Xây dựng sẵn kịch bản và thuộc lòng các câu lệnh CLI truy tìm tài nguyên rác (như ổ cứng EBS chưa dùng hay địa chỉ Elastic IP đang rảnh rỗi) là kỹ năng thực hành quan trọng cho bất kỳ kỹ sư vận hành hệ thống đám mây nào.

---

*Tham khảo: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
