# BÁO CÁO THỰC HÀNH KIỂM THỬ HIỆU NĂNG VỚI APACHE JMETER

- **Họ và tên:**Lê Quang Anh
- **Mã sinh viên:** 23010275
- **Môn học:** Kiểm thử và Đánh giá chất lượng phần mềm

---

## 1. Giới thiệu công cụ Apache JMeter
Apache JMeter là một công cụ mã nguồn mở dựa trên nền tảng Java, được thiết kế chuyên dụng để kiểm thử hiệu năng, độ tải (Load Testing) và đo lường khả năng phản hồi của hệ thống phần mềm dưới nhiều cấp độ người dùng truy cập đồng thời.

## 2. Kịch bản kiểm thử (Test Scenario)
- **Mục tiêu kiểm thử:** Kiểm thử tải endpoint API công khai `https://reqres.in/api/users?page=2`.
- **Cấu hình Thread Group:**
  - Số người dùng mô phỏng (Number of Threads): 20
  - Thời gian khởi tạo tất cả người dùng (Ramp-up Period): 5 giây
  - Số vòng lặp thực hiện (Loop Count): 2
  - Tổng số yêu cầu gửi đi: 40 requests

## 3. Kết quả thực hiện

### 3.1. Kết quả kiểm tra chức năng (View Results Tree)
Tất cả các requests gửi đến máy chủ đều được phản hồi thành công (HTTP status 200 OK), không có request nào gặp sự cố.

![View Results Tree](assets/view_results_tree.png)
*Hình 1: Chi tiết từng Request/Response trong View Results Tree*

### 3.2. Báo cáo tổng hợp hiệu năng (Summary Report)
![Summary Report](assets/summary_report.png)
*Hình 2: Bảng thống kê hiệu năng trong Summary Report*

**Phân tích các chỉ số chính:**
- **Samples (Tổng số mẫu):** 40 requests được thực thi trọn vẹn.
- **Error %:** 0.00% (hệ thống xử lý tải không có lỗi).
- **Throughput (Thông lượng):** Tốc độ xử lý yêu cầu của hệ thống đạt độ ổn định cao.

## 4. Kết luận
Kịch bản kiểm thử tải với 20 người dùng đồng thời đã diễn ra ổn định, thời gian phản hồi tốt và không có hiện tượng nghẽn mạng hay lỗi server. Kịch bản `.jmx` được đính kèm trực tiếp trong thư mục gốc của repository.
