# Tài liệu thiết kế ca sử dụng - Payroll System

## 1. Mục tiêu hệ thống
Hệ thống **Payroll System** được xây dựng nhằm:
- Tự động hóa quy trình quản lý nhân sự và tính toán lương.
- Đảm bảo tính chính xác, minh bạch và hiệu quả.
- Tăng cường bảo mật thông tin và phân quyền truy cập.

---

## 2. Danh sách các ca sử dụng

### **Bảng tổng hợp ca sử dụng**

| Mã Use Case | Tên Use Case              | Actor               | Mô tả ngắn gọn                              |
|-------------|---------------------------|---------------------|---------------------------------------------|
| UC1         | Quản lý nhân viên         | Admin, HR Staff     | Thêm, sửa, xóa thông tin nhân viên.         |
| UC2         | Quản lý điểm danh         | Employee, Manager   | Ghi nhận giờ làm, trạng thái nghỉ phép.     |
| UC3         | Tính toán lương           | System              | Tự động tính toán lương theo quy định.      |
| UC4         | Xuất báo cáo bảng lương   | HR Staff, Manager   | Xuất báo cáo chi tiết hoặc tổng hợp.        |
| UC5         | Xác thực người dùng       | Admin, User         | Đăng nhập và phân quyền truy cập.           |

---

## 3. Chi tiết từng ca sử dụng

### **UC1: Quản lý nhân viên**
- **Mục tiêu**: 
  Quản lý danh sách nhân viên, cho phép thêm mới, chỉnh sửa, hoặc xóa thông tin nhân viên.
- **Actor**: 
  Admin, HR Staff.
- **Luồng sự kiện chính**:
  1. Người dùng (Admin hoặc HR Staff) đăng nhập vào hệ thống.
  2. Người dùng chọn chức năng "Quản lý nhân viên".
  3. Người dùng thực hiện:
     - Thêm nhân viên mới bằng cách nhập thông tin.
     - Chỉnh sửa thông tin nhân viên hiện tại.
     - Xóa nhân viên khi cần thiết.
  4. Hệ thống lưu lại thay đổi và hiển thị danh sách cập nhật.
- **Điều kiện tiền đề**: 
  Người dùng đã được cấp quyền truy cập.
- **Kết quả**: 
  Danh sách nhân viên được cập nhật thành công.

---

### **UC2: Quản lý điểm danh**
- **Mục tiêu**: 
  Theo dõi thời gian làm việc, ghi nhận điểm danh, và trạng thái nghỉ phép.
- **Actor**: 
  Employee, Manager.
- **Luồng sự kiện chính**:
  1. Nhân viên đăng nhập và ghi nhận giờ làm việc thông qua hệ thống.
  2. Nhân viên gửi yêu cầu nghỉ phép (nếu cần).
  3. Quản lý duyệt hoặc từ chối yêu cầu nghỉ phép.
  4. Hệ thống ghi nhận kết quả duyệt và cập nhật trạng thái nghỉ phép.
- **Điều kiện tiền đề**: 
  Nhân viên đã có tài khoản hợp lệ.
- **Kết quả**: 
  Điểm danh hoặc trạng thái nghỉ phép được ghi nhận.

---

### **UC3: Tính toán lương**
- **Mục tiêu**: 
  Tự động tính toán lương dựa trên thông tin bảng điểm danh và quy tắc tính lương.
- **Actor**: 
  Hệ thống (System).
- **Luồng sự kiện chính**:
  1. Hệ thống tổng hợp dữ liệu từ bảng điểm danh và trạng thái nghỉ phép.
  2. Áp dụng các quy tắc:
     - Lương cơ bản.
     - Phụ cấp.
     - Thuế và khấu trừ.
  3. Tính toán tổng lương cho từng nhân viên.
  4. Lưu kết quả và tạo bảng lương.
- **Điều kiện tiền đề**: 
  Dữ liệu điểm danh và thông tin nhân viên phải đầy đủ.
- **Kết quả**: 
  Bảng lương chi tiết được tính toán và lưu trữ.

---

### **UC4: Xuất báo cáo bảng lương**
- **Mục tiêu**: 
  Tạo báo cáo bảng lương chi tiết hoặc tổng hợp.
- **Actor**: 
  HR Staff, Manager.
- **Luồng sự kiện chính**:
  1. Người dùng đăng nhập và chọn chức năng "Xuất báo cáo".
  2. Người dùng chọn loại báo cáo cần xuất:
     - Báo cáo chi tiết theo nhân viên.
     - Báo cáo tổng hợp theo phòng ban.
  3. Hệ thống xử lý và xuất file (PDF/Excel).
- **Điều kiện tiền đề**: 
  Dữ liệu bảng lương đã được tính toán.
- **Kết quả**: 
  Báo cáo được tạo và sẵn sàng tải xuống.

---

### **UC5: Xác thực người dùng**
- **Mục tiêu**: 
  Đảm bảo quyền truy cập chỉ được cấp cho người dùng hợp lệ.
- **Actor**: 
  Admin, User.
- **Luồng sự kiện chính**:
  1. Người dùng nhập thông tin đăng nhập (username, password).
  2. Hệ thống xác thực thông tin.
  3. Nếu thành công, người dùng được cấp quyền truy cập dựa trên vai trò (Admin, HR, Employee).
- **Điều kiện tiền đề**: 
  Tài khoản người dùng đã được tạo trước đó.
- **Kết quả**: 
  Người dùng được đăng nhập và sử dụng hệ thống theo phân quyền.

---

## 4. Kết luận
Tài liệu này mô tả chi tiết các ca sử dụng của hệ thống **Payroll System**, bao gồm các luồng hoạt động chính và vai trò của từng actor. Mỗi thiết kế đều đảm bảo đáp ứng yêu cầu chức năng và phi chức năng, đồng thời hỗ trợ hệ thống mở rộng trong tương lai.
