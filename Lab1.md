# Lab 1 - Kết quả thực hành

## 1. Phân tích kiến trúc
### a. Đề xuất kiến trúc: Kiến trúc MVC (Model-View-Controller)

Kiến trúc MVC là một trong những kiến trúc phổ biến nhất trong các ứng dụng desktop hoặc web, đặc biệt phù hợp với các hệ thống có giao diện người dùng rõ ràng và cần tách biệt giữa logic xử lý dữ liệu và giao diện hiển thị. Đối với bài toán Payroll System, MVC sẽ giúp quản lý các thành phần của hệ thống một cách rõ ràng, dễ dàng mở rộng và bảo trì.

### b. Vì sao chọn kiến trúc MVC:
- **Tách biệt rõ ràng:** Giao diện người dùng (View) tách biệt hoàn toàn với logic nghiệp vụ (Model) và điều khiển luồng thông tin (Controller). Điều này giúp dễ dàng cập nhật giao diện mà không ảnh hưởng đến logic nghiệp vụ.
- **Dễ dàng mở rộng:** Khi hệ thống cần mở rộng thêm chức năng, chỉ cần thêm hoặc chỉnh sửa một trong ba thành phần mà không ảnh hưởng đến các thành phần còn lại.
- **Tái sử dụng và bảo trì:** Kiến trúc này cho phép tái sử dụng các thành phần và giúp việc bảo trì dễ dàng hơn.

### c. Ý nghĩa từng thành phần.
- **Model:**
  - **Employee:** Chứa thông tin về nhân viên, bao gồm thông tin cá nhân và thông tin tiền lương.
  - **Timecard:** Chứa thông tin về thời gian làm việc của nhân viên, bao gồm số giờ làm việc và mã số dự án.
  - **Payroll:** Tính toán và lưu thông tin về bảng lương của nhân viên cho từng kỳ trả lương.
  - **PurchaseOrder:** Chứa thông tin về đơn hàng và doanh số cho nhân viên hưởng hoa hồng.
  
- **View:**
  - **EmployeeView:** Giao diện cho nhân viên để nhập thông tin thời gian làm việc, xem bảng lương, và thay đổi thông tin cá nhân.
  - **AdminView:** Giao diện cho quản trị viên để quản lý thông tin nhân viên, thêm, xóa và sửa đổi thông tin.

- **Controller:**
  - **PayrollController:** Xử lý các yêu cầu liên quan đến tiền lương, như tính toán lương cho nhân viên và tạo bảng lương.
  - **EmployeeController:** Xử lý các yêu cầu từ nhân viên để cập nhật thông tin cá nhân và gửi thông tin thời gian làm việc.

### d. Biểu đồ package.
![Diagram](https://www.planttext.com/api/plantuml/png/X5JDJkCm4BxdAInExO4NY102iNj0WjsAHN0Ux6bZrN-QiHT5Y2VZm2FjAwoJ9gr38k53gyut-Nx6a_xx-BpY21IJDLK0kOSTYhDxhz2SYRTAv2CDC8kVDXZV8Wx5_k1GkrMr-1D9kzq9Ss1nNWMb29ddG83Meelt61k_mCPWWDfQR8s7U2fBRwrcrjuzGCGPtFX4_EnfZvdoJdEyUDGM9P2wB9GJoGOOVvD2ug5lKnOFpUzLCOsHfvo6wYtyo9zV7CnjDq0x_9Ni2z8awqHZ0orvOqg97JgaB310gtKj_dgj2cOmCfb3nsgydlfuUUlIobIi3FnTAh0-kJZbocp7zNdI-BgyFHqoOTSS3BJZE5Vh6NICUa9Iw4njo6-rmG6OXBbMLhklKXPSDZSQuP9m7Ei31a-HZvHbfXllOcS4QPfiy7U2Iyr0NkPrNyXGtAHiKEvvASTeTfcSqulLSMbqXm6DJz-whIyZzI-tE3-_5Fs8wg6Tg_vdLo_qCihvIxkGObNKkxO3KTrDLeT-wxXR5wYkqAdk_-G_0000__y30000)

## 2. Cơ chế phân tích
### a. Cơ chế xác thực và phân quyền:
- **Mô tả:** Đảm bảo chỉ nhân viên và quản trị viên hợp lệ mới có quyền truy cập vào hệ thống và chỉ có thể chỉnh sửa thông tin của riêng mình.
- **Lý do:** Bảo vệ dữ liệu cá nhân và thông tin nhạy cảm trong hệ thống tiền lương.

### b. Cơ chế quản lý thời gian làm việc:
- **Mô tả:** Cho phép nhân viên nhập thông tin thời gian làm việc qua timecard và gửi thông tin cho hệ thống.
- **Lý do:** Đảm bảo tính chính xác trong việc tính toán lương dựa trên thời gian làm việc của nhân viên.

### c. Cơ chế truy cập cơ sở dữ liệu:
- **Mô tả:** Giao tiếp với cơ sở dữ liệu hiện tại (DB2) để lấy thông tin dự án và mã số dự án mà không cập nhật dữ liệu.
- **Lý do:** Tận dụng thông tin hiện có mà không gây ảnh hưởng đến hiệu suất của hệ thống.

### d. Cơ chế thanh toán tự động:
- **Mô tả:** Hệ thống tự động tạo bảng lương và thanh toán cho nhân viên vào các ngày đã định mà không cần can thiệp thủ công.
- **Lý do:** Giảm thiểu sai sót và tiết kiệm thời gian cho quản trị viên.

### e. Cơ chế thông báo:
- **Mô tả:** Thông báo cho nhân viên về các thay đổi liên quan đến bảng lương hoặc thông tin tài khoản.
- **Lý do:** Đảm bảo nhân viên luôn được cập nhật thông tin quan trọng liên quan đến lương và thanh toán.

### f. Cơ chế báo cáo cho nhân viên:
- **Mô tả:** Cho phép nhân viên truy cập và xem thông tin liên quan đến giờ làm việc, bảng lương, và thời gian nghỉ còn lại.
- **Lý do:** Cung cấp thông tin chính xác và kịp thời để nhân viên quản lý tài chính cá nhân.

### g. Cơ chế quản lý thông tin nhân viên:
- **Mô tả:** Quản trị viên có thể thêm, xóa và cập nhật thông tin của nhân viên trong hệ thống.
- **Lý do:** Đảm bảo rằng thông tin của tất cả nhân viên luôn được cập nhật và chính xác.

### h. Kết quả mong đợi:
- Một hệ thống tiền lương hiệu quả, bảo mật và dễ sử dụng, đáp ứng nhu cầu của nhân viên và quản trị viên tại Acme, Inc.
- Các cơ chế đảm bảo tính bảo mật, chính xác trong việc xử lý thông tin và cung cấp trải nghiệm người dùng tốt nhất.

## 3. Phân tích ca sử dụng Payment

### a. Xác định các lớp phân tích
- **Entity Classes:**
  - **Employee:** Lưu trữ thông tin của nhân viên (ID, tên, địa chỉ, phương thức thanh toán hiện tại).
  - **PaymentMethod:** Chứa thông tin về phương thức thanh toán (loại phương thức, địa chỉ nhận thư hoặc thông tin ngân hàng nếu cần).
     
- **Boundary Classes:**
  - **PaymentSelectionUI:** Giao diện cho nhân viên lựa chọn phương thức thanh toán (cung cấp form để chọn phương thức thanh toán, nhập địa chỉ hoặc thông tin ngân hàng).
     
- **Control Classes:**
  - **PaymentMethodController:** Quản lý quy trình chọn phương thức thanh toán và xử lý các yêu cầu từ giao diện người dùng. Kiểm tra các điều kiện (như thông tin tài khoản ngân hàng hợp lệ), cập nhật thông tin và gửi yêu cầu lưu trữ vào cơ sở dữ liệu.

### b. Biểu đồ tuần tự cho "Select Payment Method"
![Diagram](https://www.planttext.com/api/plantuml/png/Z9AnIWGn48RxFCMymBt05d9mM8YS22BOncou1BAJ9Su9MrjO-GowTWg2WfKfB0Bt7da2Ny5PriMzqnMhOMOot__Fa8_uFhyW6MXTEI4L-G3xLUryexKuzsiiPMZWM3QLHZhHJYko7ayFXF98mRkXjTHaVBdeYqu7mJLBpJVhAzzwBiJGXjdUBo85B7EyXPML7agRupM2CZdU8DHcyxnfSGN4-OFY8D40-TIY-CaPqNTz5d1ayjiJCY6zTZoBu79yaHDAOeBJIGpB5738Pgyge237N3Jf7k7IfaVy2xFLAc31zcgUvK3_sRkVWzd4HSzIgteQ7tECPgDtp5ATNJ7NM7OVuXC00F__0m00)

### c. Phân tích chức năng và dữ liệu
- **Employee:** Lưu trữ thông tin cá nhân của nhân viên và phương thức thanh toán hiện tại.
- **PaymentMethod:** Cung cấp danh sách các phương thức thanh toán cho nhân viên.
- **PaymentSelectionUI:** Giao diện cho phép nhân viên chọn phương thức thanh toán và nhập thông tin cần thiết.
- **PaymentMethodController:** Xử lý các yêu cầu từ người dùng và cập nhật thông tin vào cơ sở dữ liệu.

### d. Kết quả mong đợi
- Nhân viên có thể dễ dàng chọn và cập nhật phương thức thanh toán của mình, đảm bảo tính chính xác và an toàn cho các giao dịch thanh toán.


## 4. Phân tích ca sử dụng Maintain Timecard
### a. Xác định các lớp phân tích
- **Entity Classes:**

  - Employee: Chứa thông tin nhân viên và thời gian làm việc đã ghi nhận.
  - Timecard: Lưu thông tin về bảng chấm công của nhân viên (ID nhân viên, ngày, số giờ làm việc, mã charge).
- **Boundary Classes:**
  - TimecardEntryUI: Giao diện cho nhân viên nhập giờ làm việc, lựa chọn mã charge, và gửi bảng chấm công.
- **Control Classes:**

  - TimecardController: Quản lý luồng nhập dữ liệu và xử lý nghiệp vụ cho bảng chấm công. Xác thực số giờ làm việc, tạo hoặc cập nhật timecard, lưu thông tin và thực hiện logic gửi timecard.
### b. Biểu đồ tuần tự cho "Maintain Timecard"
![Diagram](https://www.planttext.com/api/plantuml/png/Z9B1IiD048Rl-nJp0hv03rAGee9wKj1ZkbcIXUnisMuAENlm83w1YAr52eM21q787Zmi-1xx1Bw2awPjOYtKMoQR-UQVB_ljFhj36ncRgun5t6e3FJN8T244w-iSuyWKS2cLu969UsXDSNNAkAO7dMtU7zLr9WmJQAKj6iQgNd_9sFe43WwtkHqu3-uP4XbfY6LmTmYOXd8nW7uefvW0f-fL0VVlcB2jvZQloTE16p_FWOTobeCbYeHKX_A3LyL4WrrrW0hkKRA_W3Qs0sSqlsYQqZfaXP8qmyqY2knV44RIpt4dRTVM9uIv9KmQt7q37_anRJhXeFoKDezC8lROkwXbsRJoGo0abS4zGUR7giRHX0Ti0_yfyJYuXMo3rodt6_jworl2QlTycNFvRsqhumQsMzDr9MFPXBy9b6kCwUfQT0N6rLt-0G00__y30000)
### c. Phân tích chức năng và dữ liệu
- Employee: Chứa thông tin nhân viên và ID để liên kết với các timecard. Hỗ trợ kiểm tra xác thực cho các timecard.
- Timecard: Lưu trữ dữ liệu bảng chấm công của nhân viên. Dữ liệu bao gồm ngày, giờ làm việc, và mã charge. Timecard sẽ chỉ cho phép thay đổi khi chưa được gửi.
- TimecardEntryUI: Cung cấp giao diện cho nhân viên để nhập giờ làm, chọn mã charge, và gửi timecard. Hiển thị thông tin lỗi và xác nhận.
- TimecardController: Điều phối quy trình tạo, cập nhật và gửi bảng chấm công. Xác minh số giờ hợp lệ và quản lý trạng thái gửi của bảng chấm công.


## 5. Hợp nhất kết quả phân tích
![Diagram](https://www.planttext.com/api/plantuml/png/Z9JFIiD04CRlUOgX5qyMx5541F7VeIAeu7NTBitIpMxSReGWdZrvy2n2guWeY1uyDGSFWRx7Fe6lu6JJQ9EcrK18ChFpopVpRVALV6xq3T4c2eJNxt4P4aq220djaIuxDB5We1arH7O5yxn971g7J60K3aWSC6cWpOolEWsuy00FGetIi1M4GiMC0Ua3Mt69KnN93j5nKPTJk9BRIWTk1LNIQ2MA1JbtCmyAfjqQZ7CJbvTuUMO5bfVNQ-cm2erDtoRN4a9__3uUoYuOV7wcU27I1wFIeMmuJ6tz5BYgAcFlsEILGvo-H43jw2agaMOAPc1EdXszXY1zl9X_Ywn5unoGTv8EQOx3aiifyzg4IuCd7F60KQ8N6TSg6rTKRE7xukEzacT5hjwk8ZjngkM4Ld2PwdtVZQ7BRN878Xq4S8wtLpJlkbem3QapnFZfHpP4BilrbO4LuHaRJkte0UifFZq6G3FOGX3sLJFv9TYroKCEVJI8mRImoMteeLDhpMRzzu2iB5ST-MBZlRd2CXbjcznmE8k81DnMLsxAR-JNyVDqCAKEUZxUEur_xFwZdp5ZZ-czHC_I5-mzQs6-HVEgl0qcEzaFwHi00F__0m00)

#### Giải thích:
- **Các package**: 
  - "Select Payment Method" và "Maintain Timecard" chứa các lớp phân tích cho từng ca sử dụng. 
  - Mỗi package đại diện cho một chức năng cụ thể trong hệ thống, giúp tổ chức và phân loại các lớp một cách rõ ràng.

- **Lớp chung**: 
  - **Employee** được thể hiện trong cả hai phần để nhấn mạnh sự chia sẻ thông tin. 
  - Lớp này chứa thông tin quan trọng về nhân viên, cho phép cả hai ca sử dụng truy cập vào cùng một nguồn dữ liệu mà không cần phải tạo ra lớp riêng biệt cho mỗi ca.

- **Mối quan hệ**: 
  - Các mũi tên thể hiện luồng thông tin và tương tác giữa các lớp, cho thấy cách mà các lớp tương tác với nhau trong hai ca sử dụng khác nhau. 
  - Điều này giúp làm rõ cách thức mà các chức năng trong hệ thống giao tiếp và phối hợp với nhau để hoàn thành nhiệm vụ.
