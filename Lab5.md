# Thiết Kế Hệ Thống Con (Subsystem Design)

## 1. Các Hệ Thống Con

### 1.1 Authentication Subsystem
- **Mục đích**: Quản lý xác thực người dùng và phân quyền truy cập.
- **Tương tác**: Cung cấp quyền truy cập cho Timecard Management, Payroll Processing, và Distribution.

### 1.2 Timecard Management Subsystem
- **Mục đích**: Quản lý thông tin chấm công của nhân viên.
- **Thành phần chính**:
  - Biểu mẫu nhập dữ liệu chấm công.
  - Cập nhật và lưu dữ liệu thời gian làm việc.
- **Tương tác**: 
  - Nhận mã dự án từ Project Management Subsystem.
  - Cung cấp dữ liệu chấm công cho Payroll Processing Subsystem.

### 1.3 Payroll Processing Subsystem
- **Mục đích**: Xử lý bảng lương và tạo phiếu lương.
- **Thành phần chính**:
  - Tính toán lương dựa trên giờ làm việc.
  - Tạo phiếu lương cho nhân viên.
- **Tương tác**:
  - Nhận dữ liệu chấm công từ Timecard Management Subsystem.
  - Gửi phiếu lương đến Distribution Subsystem.

### 1.4 Distribution Subsystem
- **Mục đích**: Phân phối phiếu lương qua ngân hàng hoặc in phiếu.
- **Thành phần chính**:
  - Gửi lệnh giao dịch tới ngân hàng.
  - Tích hợp máy in để in phiếu lương.
- **Tương tác**: Nhận dữ liệu phiếu lương từ Payroll Processing Subsystem.

### 1.5 Project Management Subsystem
- **Mục đích**: Quản lý mã dự án và cung cấp thông tin mã dự án cho Timecard Management.
- **Thành phần chính**:
  - Lưu trữ và cung cấp danh sách mã dự án (charge codes).
  - Hỗ trợ liên kết giờ làm việc với mã dự án.

## 2. Sơ Đồ Hệ Thống Con (Subsystem Diagram)
![Payroll System Subsystem Diagram](https://www.planttext.com/api/plantuml/png/X5H1ReCm4Bpp2Ykdzf0FL15AgnnwgHGfoGCsPaEi61ljsbIeoijww9FwXHe8AQaRM0aEk-Fn3BFY-_DhoGx8-K8d9SWJv2XcQwZ9QYqsDJiiPk8ZIKIew_pPkoCQfoGuPOtO-3rVaU9IKWFpN-WGq9MskJ8FZt7NUXUrAoHrg7UCD1YTa-vzAt6h2fH0cNW34nf5q32gynzyBBO0PLnuUd0aq9SPEBmxhXI-zyDNnSvIFMcaps9DLYApClceZnWUso1lBh18eGGjlGuULfXvsKJ64IP7WnGWWKCUKPucBQo2LL9xFxaiGs0icz5aBs1EMmB3q8gBzLjpK5ICGKeA8Kvf7rdn-JoTNAydiLYKP2kL8GkGJHB2sJJjk2SEjnUCntx37rOE1kpZ9rloUu4qjCrNvf1TH_BBdPoJPHWr_uaV0000__y30000)
