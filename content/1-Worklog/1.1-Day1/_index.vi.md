---
title: "Ngày 1"
date: 2026-06-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# Nhật ký ngày đầu: Tạo tài khoản, nhận Credit trải nghiệm và thử nghiệm các dịch vụ cơ bản

> **Ngày 1 - Thứ Hai, 01/06/2026:** Kích hoạt thành công tài khoản AWS dành cho học tập, nhận $100 ban đầu và hoàn tất 5 bài thực hành cơ bản để nhận thêm $100 credit thưởng.

---

### Các nhiệm vụ trọng tâm trong ngày

- Hoàn tất các bước đăng ký tài khoản AWS mới và nhận **$100 credit khởi động** của chương trình.
- Thực hiện đầy đủ **5 bài lab hướng dẫn** trên bảng điều khiển AWS nhằm tích lũy thêm **$100 credit** khuyến khích (mỗi lab tương ứng $20).
- Tiếp cận trực tiếp và bước đầu nắm được cơ chế hoạt động của 5 dịch vụ nền tảng: EC2, Bedrock, Budgets, Lambda, cùng với RDS.
- Thực hành dọn dẹp tài nguyên ngay sau khi test để rèn luyện thói quen tối ưu hóa chi phí.

---

### Task 1: Tạo và cấu hình máy chủ ảo Amazon EC2 (Tích lũy $20 Credit)

**Mục tiêu:** Thực hành khởi tạo, kiểm tra trạng thái hoạt động và hủy một máy chủ ảo chạy trên đám mây.

**Tổng quan dịch vụ:** **Amazon EC2 (Elastic Compute Cloud)** mang lại giải pháp máy chủ ảo có khả năng tự thay đổi quy mô linh hoạt. Người dùng có toàn quyền tùy biến hệ điều hành, cấu hình phần cứng (CPU, RAM) và thiết lập bảo mật.

**Các bước thực hiện:**
1. Trên trang chủ **AWS Console** → đi tới phần **Explore AWS** → chọn bài thực hành **Launch an instance using EC2**.
2. Nhấn **Start activity** để bắt đầu quy trình lab.
3. Cấu hình các thông số máy chủ:
   - Tên máy chủ (Name tag): Thiết lập tên `FCA-Test-Server`.
   - Hệ điều hành (AMI): Lựa chọn Amazon Linux 2023 (loại miễn phí - Free Tier eligible).
   - Loại tài nguyên (Instance Type): Dùng cấu hình nhỏ nhất là `t2.micro` hoặc `t3.micro`.
4. Tạo Key Pair để truy cập máy chủ từ xa an toàn:
   - Đặt tên key: `fca-keypair`
   - Loại thuật toán mã hóa: **RSA**
   - Định dạng file: **.pem** (tải và cất giữ cẩn thận trên máy cá nhân).
5. Thiết lập Security Group với các cấu hình rule mặc định để cho phép các truy cập cơ bản.
6. Xem lại thông tin cấu hình rồi ấn **Launch Instance**.
7. **Kiểm tra:** Đợi vài phút rồi vào danh sách EC2 check xem máy ảo đã chuyển sang trạng thái **Running** và vượt qua cả **2/2 status checks** hay chưa.
8. **Dọn dẹp hệ thống:** Chọn instance vừa chạy → Instance State → Nhấp **Terminate Instance** để xóa sạch máy chủ ảo.

> **Bài học rút ra:** Việc tạo mới tài nguyên trên AWS cực kỳ đơn giản và nhanh chóng. Tuy nhiên, để tránh bị trừ phí ngầm, cần nhớ xóa máy chủ ngay khi không dùng đến, đồng thời đảm bảo phân vùng lưu trữ EBS đi kèm cũng được hủy bỏ hoàn toàn.

---

### Task 2: Trải nghiệm tương tác prompt trên Amazon Bedrock Playground (Tích lũy $20 Credit)

**Mục tiêu:** Tìm hiểu cách giao tiếp với các mô hình ngôn ngữ lớn (LLM) trên nền tảng AWS.

**Tổng quan dịch vụ:** **Amazon Bedrock** cung cấp một cổng kết nối hợp nhất giúp người dùng gọi các mô hình AI tạo sinh từ các đối tác lớn như Anthropic, Meta, Cohere thông qua API mà không cần tự thiết lập máy chủ xử lý.

**Các bước thực hiện:**
1. Di chuyển tới giao diện điều khiển **Amazon Bedrock** → tìm đến phần thực hành **Use a foundation model in Amazon Bedrock**.
2. Tìm kiếm và gửi yêu cầu đăng ký truy cập mô hình **Claude 3 Haiku** (phiên bản tối ưu về tốc độ phản hồi và chi phí).
3. Nếu hệ thống yêu cầu xác nhận lý do sử dụng, hãy viết một đoạn mô tả ngắn gọn mục đích thực hành rồi gửi yêu cầu kích hoạt.
4. Khi đã có quyền truy cập, mở công cụ **Text Playground** lên và chọn mô hình **Claude 3 Haiku**.
5. Gõ một prompt thử nghiệm (ví dụ: "Hãy tóm tắt ngắn gọn 3 điểm mạnh của công nghệ đám mây") rồi nhấn **Run**.
6. Quan sát phản hồi, thử thay đổi các thông số như Temperature (độ sáng tạo của mô hình) và nhấn **Finish** để lưu lại tiến trình.

> **Bài học rút ra:** Để sử dụng các công cụ Generative AI trên AWS, người dùng cần tuân thủ các quy tắc an toàn thông tin. Việc viết lý do sử dụng rõ ràng sẽ giúp tiến trình xét duyệt diễn ra nhanh hơn.

---

### Task 3: Tạo cảnh báo hạn mức chi tiêu bằng AWS Budgets (Tích lũy $20 Credit)

**Mục tiêu:** Thiết lập công cụ kiểm soát chi phí tự động giúp ngăn ngừa hóa đơn phát sinh ngoài tầm kiểm soát.

**Tổng quan dịch vụ:** **AWS Budgets** là dịch vụ theo dõi và gửi thông báo qua email hoặc SMS cho người dùng khi lượng chi phí thực tế hoặc dự báo của tài khoản vượt quá định mức thiết lập sẵn.

**Các bước thực hiện:**
1. Truy cập **AWS Billing Console** → di chuyển đến phần **Budgets** → chọn bài lab **Set up a cost budget using AWS Budgets**.
2. Click chọn **Start activity** để bắt đầu quy trình tạo ngân sách.
3. Thiết lập các thông số cơ bản:
   - Loại ngân sách: Chọn Cost budget (Theo dõi bằng chi phí).
   - Chu kỳ: Thiết lập Monthly (Hàng tháng).
   - Ngưỡng ngân sách giới hạn: Nhập vào mức $20.00.
4. Thiết lập quy tắc gửi thông báo:
   - Đặt ngưỡng cảnh báo khi chiêu thực tế đạt **80% ($16.00)** định mức.
   - Điền địa chỉ email cá nhân vào ô người nhận thông tin cảnh báo.
5. Kiểm tra kỹ các thông tin đã thiết lập rồi ấn **Create budget** để khởi tạo.

> **Bài học rút ra:** Cài đặt ngân sách cảnh báo là bước phòng vệ thiết yếu đối với bất kỳ tài khoản Cloud nào. Công cụ này giúp bạn phát hiện sớm các tài nguyên chưa được dọn dẹp trước khi chúng dùng hết credit được cấp.

---

### Task 4: Triển khai ứng dụng Serverless bằng AWS Lambda (Tích lũy $20 Credit)

**Mục tiêu:** Viết và khởi chạy mã nguồn ứng dụng trên mô hình Serverless không cần quản trị hạ tầng.

**Tổng quan dịch vụ:** **AWS Lambda** cho phép thực thi mã nguồn dựa trên các sự kiện kích hoạt (như yêu cầu từ Web) mà không cần bận tâm về việc thiết lập máy chủ bên dưới. Hệ thống chỉ tính phí khi code thực sự chạy, và chi phí tự động giảm về 0 khi không có người dùng truy cập.

**Các bước thực hiện:**
1. Đi tới **AWS Lambda Console** → chọn bài thực hành **Create a web app using AWS Lambda**.
2. Nhấn **Start activity** → chọn **Use a blueprint** (sử dụng mẫu có sẵn) → tìm kiếm template **Getting started with Lambda HTTP**.
3. Cấu hình cho Function mới:
   - Đặt tên hàm: `fca-http-lambda-app`
   - Xác nhận tạo mới một Role IAM đi kèm để cấp các quyền thực thi cơ bản cho hàm Lambda.
4. Chọn nút **Create function** rồi đợi hệ thống tạo xong tài nguyên.
5. **Kiểm tra:** Sao chép đường dẫn **Function URL**, mở một tab mới trên trình duyệt và dán đường dẫn này vào để verify xem hàm có phản hồi về một chuỗi kết quả JSON chào mừng hay không.
6. **Dọn dẹp:** Xóa hàm Lambda vừa tạo để giữ sạch môi trường lab.

> **Bài học rút ra:** Mô hình Serverless giúp loại bỏ hoàn toàn các công việc liên quan đến cài đặt hệ điều hành hay vá lỗi bảo mật máy chủ. Khi không có lượt truy cập, hệ thống hoàn toàn miễn phí.

---

### Task 5: Tạo cơ sở dữ liệu quan hệ được quản trị với Amazon RDS (Tích lũy $20 Credit)

**Mục tiêu:** Thiết lập và quản lý một hệ quản trị cơ sở dữ liệu quan hệ an toàn trên cloud.

**Tổng quan dịch vụ:** **Amazon RDS (Relational Database Service)** giúp tự động hóa hầu hết các công việc quản trị database phức tạp như backup định kỳ, cập nhật phiên bản vá lỗi và thiết lập các bản sao dự phòng chống sự cố.

**Các bước thực hiện:**
1. Di chuyển vào trang quản trị **Amazon RDS** → chọn bài thực hành **Create an Amazon RDS Database**.
2. Sử dụng tùy chọn **Easy create** để dùng các thiết lập mặc định được tối ưu sẵn.
3. Thiết lập thông số Database:
   - Engine cơ sở dữ liệu: Chọn **Aurora (PostgreSQL Compatible)**.
   - Instance Class: Lựa chọn loại cấu hình máy chủ nhỏ nhất có sẵn.
4. Nhấn nút **Create database** và chờ cho tới khi trạng thái của DB chuyển từ tạo mới sang **Available**.
5. **Quy trình dọn dẹp (Lưu ý tuân thủ trình tự):**
   - Bạn không thể xóa Cluster trực tiếp khi các DB instance bên trong vẫn còn hoạt động.
   - Đầu tiên, chọn DB instance con (`database-1-instance-1`) và thực hiện thao tác xóa (Delete), bỏ chọn phần tạo snapshot cuối kỳ để quá trình xóa diễn ra nhanh hơn.
   - Chờ instance con biến mất hoàn toàn, sau đó mới thực hiện xóa Cluster chi (`database-1`).

> **Bài học rút ra:** Khi làm việc với cơ sở dữ liệu trên cloud, cần lưu ý đến mối liên hệ phụ thuộc giữa các tài nguyên. Luôn luôn xóa các instance con trước rồi mới có thể xóa cluster tổng thể.

---

### Báo cáo kết quả & Bài học kinh nghiệm ngày đầu

- **Kết quả tích lũy:** Nhận $100 credit ban đầu cùng với $100 credit thưởng sau khi hoàn thành 5 bài lab hướng dẫn (Tổng cộng tài khoản có **$200**).
- **Kỹ năng đạt được:** Làm quen và hiểu được cách thức hoạt động của các dịch vụ cốt lõi từ tính toán (EC2), trí tuệ nhân tạo (Bedrock), quản lý tài chính (Budgets), serverless (Lambda) đến lưu trữ dữ liệu quan hệ (RDS).
- **Tư duy tối ưu hóa chi phí:** Hình thành phản xạ dọn dẹp, tắt hoặc xóa bỏ các tài nguyên ngay sau khi thử nghiệm xong. Quên xóa một instance RDS hay máy chủ EC2 có thể làm hao hụt lượng credit cực kỳ nhanh chóng.
- **Phương pháp học chủ động:** Tận dụng các bài lab hướng dẫn trực tiếp trên giao diện console của AWS là cách nhanh nhất và an toàn nhất để bắt nhịp với môi trường đám mây.

---

*Tham khảo: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
