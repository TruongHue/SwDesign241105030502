# Lab 2 - Kết quả thực hành

# I. Phân tích các ca sử dụng
## 1. Phân tích ca sử dụng Create Employee

### a. Xác định các lớp phân tích
- **Entity Classes:**
  - **Employee:** Tên, giờ làm việc, mức lương, số ngày nghỉ.
  - **Project:** mã dự án, tên dự án, danh sách số giờ làm việc của nhân viên trong dự án.
  - **Report:** Chứa các dữ liệu cho từng loại báo cái, gồm loại báo cáo, khoảng thời gian, chi tiết ngày nghỉ và tổng lương.
     
- **Boundary Classes:**
  - **ReportEntryUI:** Giao diện cho Employee để nhập tiêu chí tạo báo cáo (loại báo cáo, ngày bắt đầu và kết thúc, mã dự án nếu cần), và thực hiện các thao tác như xem, lưu hoặc huỷ báo cáo.
     
- **Control Classes:**
  - **ReportController:** Quản lý quá trình tạo báo cáo từ thông tin nhập vào, kiểm tra tính hợp lệ của dữ liệu, lấy thông tin từ các lớp khác (như Employee hoặc Project), và thực hiện lưu báo cáo nếu được yêu cầu. 
 
### b. Biểu đồ tuần tự cho "Create Timecard"
![Diagram](https://www.planttext.com/api/plantuml/png/b5NDRjD04BxlKunwRbyWKb15g2YYgYe41uxEPXKRdDrqEuxa8-B00N7e0o0IAbG9Y029a_VGmrQynpu1hy3OJkArdJzyi9pHVjz-Cz_CvA-vExx2G6CoYbd0KMau6OrZbGh1-YgHWq2dy4oCbSOJYJfzyOHnHHygNaHxvQzOQ2OaHfYky8y239Qn2wrU2Ov-g8Gprkt2qz2PJn6WosOABXCx0zJskmmNaRwb5yzVtIvZIteuUb0Nre4UyNoGSD3J8a2n4h8uTi1gntFyyaG7Njgl2N2NtIOWGvVDnu1H4Ghjl1AmxVBp4XOhqXnvcYTs2d9efodqNVO3uVuwl-KGNhli3W53ct4Mn0WFLmWCXOA1Cx_0pYG3Ubh2lNfsuCnbNr8O15ImAplZ8OpiJHtl7OUZjlJdscKtC77cpLQM_Sh7InDQwDs-rI123bZRi6RFTU2nC_DelLdDmxvaltBamMyv90v9tjlF4YR49lSqfKw_nXUFVHWvyn5YEntH5SwyuzJWvbixRr-avvUVjcVP1lbhqozZ16yCLf5TLSG5TiFTLL7khqbwCQJ579zIKcybaJdplkZx-C_Ff36-crMjsg56Kw5vgAhTjBkRwdV_v-nJ0Oi49ha4MaRpWcwFyT-4tB-JjnAiT_EidcgnKgljGXirNIxK7Glqr9dRjBbrsJ7rPFxty0y00F__0m00)

### c. Phân tích chức năng và dữ liệu
- **Employee:** Cung cấp dữ liệu liên quan đến giờ làm việc, mức lương, và ngày nghỉ của nhân viên, giúp hệ thống tạo các báo cáo về thời gian làm việc và lương.
- **Project:** Cung cấp dữ liệu về mã dự án và số giờ nhân viên làm việc trên dự án đó, giúp hệ thống tạo báo cáo giờ làm việc theo dự án.
- **Report:** Chứa dữ liệu của từng báo cáo, bao gồm loại báo cáo, khoảng thời gian, và các thông tin khác (số giờ làm việc, ngày nghỉ, tổng lương). Đối tượng này giúp hệ thống tổ chức và lưu trữ thông tin cần thiết để hiển thị hoặc lưu trữ báo cáo.
- **ReportEntryUI:** Giao diện giữa hệ thống và Employee để nhập và điều chỉnh các thông tin cần thiết, thực hiện các thao tác xem, lưu hoặc huỷ báo cáo.
- **ReportController:** Điều phối quy trình tạo, hiển thị, và lưu báo cáo. Đảm bảo thông tin đầu vào hợp lệ, tạo báo cáo dựa trên tiêu chí, và điều khiển quá trình lưu báo cáo nếu được yêu cầu.

### d. Kết quả mong đợi
- **Tạo báo cáo thành công:** Báo cáo được tạo theo tiêu chí yêu cầu, hiển thị cho Employee xem.
- **Lưu báo cáo:** Báo cáo được lưu với tên và vị trí do Employee chỉ định.
- **Thông báo lỗi:** Hệ thống hiển thị lỗi nếu thông tin không đầy đủ hoặc không hợp lệ.
- **Hủy báo cáo:** Báo cáo bị hủy nếu Employee không chọn lưu.
- **Trạng thái hệ thống không đổi:** Không có thay đổi lâu dài trong hệ thống sau khi tạo báo cáo.


## 2. Phân tích ca sử dụng Maintain Purchase Order

### a. Xác định các lớp phân tích
- **Entity Classes:**
    - **PurchaseOrder:** Chứa thông tin chi tiết của đơn hàng mua như điểm liên hệ khách hàng, địa chỉ thanh toán, danh sách sản phẩm, ngày mua, trạng thái đơn hàng, và mã đơn hàng duy nhất.
    - **CommissionedEmployee:** Lưu thông tin của nhân viên hưởng hoa hồng, bao gồm thông tin cần thiết để truy cập và duy trì các đơn hàng mua.
     
- **Boundary Classes:**
  - **PurchaseOrderUI:** Giao diện người dùng để nhân viên nhập các thông tin liên quan tới đơn hàng mua, cũng như lựa chọn các chức năng như tạo, cập nhật, hoặc xóa đơn hàng.
     
- **Control Classes:**
  - **PurchaseOrderController:** Kiểm soát và quản lý các quy trình tạo, cập nhật và xóa đơn hàng mua, bao gồm việc kiểm tra quyền truy cập của nhân viên đối với đơn hàng và xử lý các yêu cầu từ nhân viên. 

### b. Biểu đồ tuần tự cho "Maintain Purchase Order"
![Diagram](https://www.planttext.com/api/plantuml/png/x5RDQjj04BxhAOQS4d1VmE0IgXWI-cE3KqYFMrbOYwMLAgr2VImvX18A2JsKqaFicX0IKdf8eI1HSbZJzzWdw2jqTcpBLcpJXDvA3TBAcc_-llcarQ_yPZEHB9Pfu5lCaM4CTXW4F4buADnsFOZyiEUwm1AmwrQ4GExmY0a9hLuYtS0OMgNxpJHsF9QuZRZjniRSR5XMhGQFFPsVSXYTwFoZwC2hL0r0nkfAU7Yjiw40N_r0yy-104_r4HAa36erowx3WuVGgi8ZdNsL9a1sdiBQKyQ5nAD829HnpMePk5slmWjrcO93Q0UJlnEqN3WWHWSOVdrNPuEm0hRElaGWF5maUA7ElZkmfwxPXcKnNmAXRjTb0VwAmknnz3KxTfb4hXPACkXbPKbFVSE04hkOJx3-XAjB_AFpG-XwQk1uOqE5s3jYrCTRz6P8dWpLG5GW8GeZxE8Yg83eg7vlurQLAOR6l6VHYhopCfkDwgJlPWC2dN_Yi4_dESTzrOSEfeP03KlLjzCUiNacottlnbYYYVDcmOLIM9Rh8sMbSTo9zkTH-twqxsmjj5q4VUPH_YMG6JFgAe0krzbDiA3NCKqxM-HXv3CwdW6w4_Pq_bxWEHlmgTuc5ZE-8SSgytE65AZFIBEH0aKhTRFDTNw0GP22e-bKNYeScA_p3vpmnEPy-j49qQwk9mtzTK0Ssodf09s6aK4UtYtmCk6LHpilWZyu5NCfEQ5m5oGxbXcr8jeJkPad_Muost9zzx_C_WMP5Kvx-6uT2qR0QnH2WJ2KhZIM1ZawDZHt0FUk1L0nIX8PxeDJ0xMuZVJtLZXHHsJ7btm8qfHIGXe1JrSIizbXKIhqj6JEFRRNMRuGRnltFlgitbutCPtvMFWD003__mC0)

### c. Phân tích chức năng và dữ liệu
- **PurchaseOrder:** Lưu trữ thông tin chi tiết của từng đơn hàng mua, bao gồm mã đơn hàng duy nhất, điểm liên hệ khách hàng, địa chỉ thanh toán, danh sách sản phẩm và trạng thái đơn hàng. Lớp này cung cấp các thông tin cần thiết để tạo, cập nhật, và xóa đơn hàng.
- **CommissionedEmployee:** Giữ thông tin nhân viên hưởng hoa hồng, xác định quyền truy cập và kiểm tra quyền sở hữu của đơn hàng trong quá trình duy trì đơn hàng.
- **PurchaseOrderUI:** Giao diện chính giữa hệ thống và nhân viên để nhập dữ liệu, chọn các thao tác, và xác nhận các bước trong quá trình tạo, cập nhật và xóa đơn hàng.
- **PurchaseOrderController:** Xử lý quy trình duy trì đơn hàng, kiểm tra tính hợp lệ và quyền truy cập của nhân viên, cập nhật và xác nhận thao tác xóa khi cần.

### d. Kết quả mong đợi
- **Tạo đơn hàng mua thành công:** Một đơn hàng mua mới với mã duy nhất được tạo và thêm vào hệ thống.
- **Cập nhật đơn hàng mua thành công:** Đơn hàng mua được cập nhật với thông tin mới.
- **Xóa đơn hàng mua thành công:** Đơn hàng mua được xóa khỏi hệ thống nếu có xác nhận từ nhân viên.
- **Thông báo lỗi:** Hệ thống hiển thị lỗi nếu ID đơn hàng không tồn tại, quyền truy cập bị từ chối, hoặc đơn hàng đã đóng.
- **Xác nhận trước khi xóa:** Hệ thống yêu cầu nhân viên xác nhận thao tác xóa trước khi tiến hành.

## 3. Phân tích ca sử dụng Login

### a. Xác định các lớp phân tích
- **Entity Classes:**
  - **User:** Name, Password.

- **Boundary Classes:**
  - **LoginUI:** nhập Name và Password
     
- **Control Classes:**
  - **LoginController:** Nhận thông tin đăng nhập từ LoginUI, gửi thông tin dến User để xác thực và trả về kết quả (thành công hoạc thông báo lỗi) cho LoginUI.

### b. Biểu đồ tuần tự cho "Login"
![Diagram](https://www.planttext.com/api/plantuml/png/d54zJaCn3Dvp2b-02xoXgWGCbJg1ocuIguhavnJRANfdO-18N864G6ah9Z9OilNzEVvuUr-RetgTEM3qeh0pql1SgYJK1RPbdsMt2R68Q-7Htuw66v34io-357g5czKFQO9xSLA3skQ2Cm5AWWEQlHPDuHjr8logJl18aWouZq7ffP9vk09rNZUSu0av9tI2g9Hw86Ixp78k_K1ULU0uIBbq0wli0Tc7r8KEjFU7ysd5ksm7nWMinaXcNokst90b41l1Hex_rYJLTf2voUAUsbUdi6wbd-eJ003__mC0
)

### c. Phân tích chức năng và dữ liệu
- **User:** Chứa thông tin người dùng (tên, mật khẩu). Kiểm tra thông tin đăng nhập và xác nhận tính hợp lệ của tên và mật khẩu.
- **LoginUI:** Cung cấp giao diện cho người dùng nhập thông tin đăng nhập và hiển thị kết quả (thành công hoặc lỗi).
- **LoginController:** Xử lý luồng đăng nhập và xác thực thông tin người dùng, kết nối LoginUI với lớp User để kiểm tra tính hợp lệ của thông tin.

### d. Kết quả mong đợi
- **Thành công:** Hiển thị thông báo đã đăng nhập vào hệ thống.
- **Thất bại:** Hệ thống không thay đổi và thông báo lỗi.

## 4. Phân tích ca sử dụng Create Administrative Report

### a. Xác định các lớp phân tích
- **Entity Classes:**
  - **Employee:** Tên, Id, giờ làm việc, mức lương.
  - **PaymentMethod:** Loại báo cáo, thời gian bắt đầu, thời gian kết thúc, danh sách nhân viên.
     
- **Boundary Classes:**
  - **ReportEntrynUI:** Giao diện cho Payroll Administrator nhập các tiêu chí tạo báo cáo (loại báo cáo, ngày bắt đầu và kết thúc, danh sách nhân viên) và thực hiện các thao tác như lưu hoặc huỷ báo cáo.
     
- **Control Classes:**
  - **PaymentMethodController:** Quản lý quy trình tạo báo cáo từ thông tin đầu vào, xác minh tính hợp lệ của dữ liệu nhập, và thực hiện lưu báo cáo nếu được yêu cầu. Khi dữ liệu không hợp lệ, lớp này sẽ điều hướng để Payroll Administrator bổ sung hoặc sửa dữ liệu.

### b. Biểu đồ tuần tự cho "Create Administrative Report"
![Diagram](https://www.planttext.com/api/plantuml/png/d5J1Qjj04BtlLym7f3zWS8cRXhga55FIGuwo9BnBrhjcDJBed4Ce8PGUIgznUoWKZ7ie1BI77BRaF_OB-WkTbPfASfN4L8T5EvetR-RDGx_ipNw6aS5yBbaKepOmYGgZfHmbSw54XYOAmIY3oOXDTQwIo1Jm9breWuSAJV7s9OirlMZv9tfGtsHgMAfGO067yuNKHPhUtUiyneP3UERB3SBF3xxycWFwSgLXwkY8mp4Siia8dZpjqWtWn7tB8Uw3i4vcW4v6dNp5VRbU08egnDswXUtbUbq3f2OYqIJlWPgvgmAchVxlOgU-l450xifu3v98SSZSAkR4xJuhM1ArOlyskYtU05vuknRzhMudDmK6S2IyFPi3BGuIRpSWwNwUjy2HH7ZU-iAz_K8JqZi3Ukwl_LUKSQ1GDAAt5wt2gSpIJkLJxdwesNyG7DV0gZJXFWbOkYiecZrElVq8MKuvMAUYK6Ilf3BLgzllD1Ljx3e6ddjxlOEd3gZ9ImNoVcYbMrMw2JNZF6uvMdirnJA8XeRs6SYg4Wyvxo7SpYPgARS5xlTGTqpIEDLzZSGashlWVdkXUBt-yPPekpggXddxlksdiCzzEiFFwJS0003__mC0)

### c. Phân tích chức năng và dữ liệu
- **Employee:** Cung cấp dữ liệu liên quan đến các nhân viên, giúp hệ thống lấy thông tin như giờ làm việc hoặc mức lương theo thời gian.
- **Report:** Chứa dữ liệu của từng báo cáo, gồm loại báo cáo, khoảng thời gian, và danh sách nhân viên. Đối tượng này sẽ giúp tổ chức và lưu trữ thông tin cần thiết để báo cáo có thể được hiển thị hoặc lưu trữ.
- **ReportEntryUI:** Giao diện giữa hệ thống và Payroll Administrator để nhập và điều chỉnh các thông tin cần thiết, cũng như thực hiện các thao tác liên quan như lưu hoặc huỷ báo cáo.
- **ReportController:** Điều phối quy trình tạo, hiển thị, và lưu báo cáo. Nó sẽ đảm bảo thông tin đầu vào hợp lệ, tạo báo cáo dựa trên tiêu chí, và kiểm soát quá trình lưu báo cáo nếu được yêu cầu.

### d. Kết quả mong đợi
- **Tạo báo cáo thành công:** Báo cáo được tạo theo tiêu chí yêu cầu.
- **Lưu báo cáo:** Báo cáo được lưu với tên và vị trí do người dùng chỉ định.
- **Thông báo lỗi:** Hệ thống hiển thị lỗi nếu thông tin không đầy đủ và không hợp lệ.
- **Hủy báo cáo:** Báo cáo bị hủy nếu không được lưu.
- **Trạng thái hệ thống không đổi:** Khong6 có thay đổi lâu dài trong hệ thống sau khi tạo báo cáo.


## 5. Phân tích ca sử dụng Maintain Employee Info

### a. Xác định các lớp phân tích
- **Entity Classes:**
  - **Employee:** Chứa thông tin của nhân viên, bao gồm tên, loại nhân viên (giờ, lương tháng, hoặc hưởng hoa hồng), địa chỉ, số an sinh xã hội, các khoản khấu trừ thuế và khác, số điện thoại, lương theo giờ, lương tháng, tỷ lệ hoa hồng và giới hạn giờ làm.

- **Boundary Classes:**
    - **EmployeeUI:** Giao diện người dùng cho Payroll Administrator để nhập thông tin, chọn các chức năng như thêm, cập nhật hoặc xóa thông tin nhân viên.     
- **Control Classes:**
    - **EmployeeController:** Quản lý quá trình thêm, cập nhật và xóa thông tin nhân viên, xử lý các yêu cầu từ Payroll Administrator và thực hiện xác nhận nếu cần thiết.
### b. Biểu đồ tuần tự cho "Maintain Employee Info"
![Diagram](https://www.planttext.com/api/plantuml/png/x5NTYjD05BxFKnnwjGkn3r2eRDqMjeYba0hhvPZ4PcWoYUcas4lfbIp2Bbw8UE7MfIpM5IzM419aBwOlCa_WAtXckls9RNGBNbheJCZv-RxpdPEPdzdDGP-Jc2U1Rn2RXp6qoJ0EVR_c19JHFe-9UadwqAuP4JfIcqQ4SR26VUu6oc3btZU2o0-7hgii3SEeLk6X9xCF56PdCdl7kl0y4MFWiRXY7ZxBz8A1Btu0zyGtj7BAW7dY8uC15LC6rQhHhi6z-s1Lu85CltAL9xrCeFI8KCRnlq9iicTX711EGrOoB1NKhbNWYPWcOEiO6vcyPdhxP0ERZH1mh-E9QM32eKo_H0YD6mSlbEbt6ux5DTat3E9pq5xhp0p0tvBQuJnpgUOuG5QKIjfh6vM2SlSuhYRuY3-cfjRiX6Z2hqpeo-mCBAjbWYt6DlGKIrIlXvmdc36MsMSJokNo_c_S4WH2r4bKWBeYsQX01v73bQQ1pDvJ6EXrBNeWpg4hnWm2SP4hm4c6MiG9pvVUYP6holDo8qH368Rhzzry5_x0TaFunv53k7itxPlrudmjJpFOuh8KI5m5qAColGcAkZYNgrdNSMfwMcl6tcsCpDumNB7FsYr7zeZAR8HMBEva0V9KO5zycRsT-skvrlFkd72RhdbjxzYCTNLoCSifsfYVUSzr7SovxRtwsdRgUTtrtVyz_oSztoRP2tN8w4uoVBucIsTLtN6HCQVix5GHx0AUxnjE2srdftYEUE3eGsnTKNNuZV9nMe0ZcLqE2_BfkhMTUoG4hbZcC-2uBNOzUkg2mhxg0K_jtM-d5MmepfNQk7f_lPqE45jTkRy0003__mC0)

### c. Phân tích chức năng và dữ liệu
- **Employee:** Chứa các thuộc tính của nhân viên và lưu giữ các thông tin cần thiết như mã nhân viên, thông tin cá nhân, loại nhân viên và các chi tiết khác cho phép tính toán lương và khấu trừ.
- **EmployeeUI:** Đóng vai trò là giao diện giữa Payroll Administrator và hệ thống, giúp nhập thông tin và lựa chọn thao tác liên quan đến nhân viên.
- **EmployeeController:** Điều khiển các quy trình thêm, cập nhật và xóa nhân viên; thực hiện các kiểm tra hợp lệ, xử lý lỗi và xác nhận thao tác trước khi thực hiện thay đổi trong hệ thống.

### d. Kết quả mong đợi
- **Thêm nhân viên thành công:** Một nhân viên mới được thêm vào hệ thống với mã nhân viên duy nhất và phương thức nhận lương mặc định là “pickup”.
- **Cập nhật thông tin nhân viên thành công:** Thông tin nhân viên được cập nhật với dữ liệu mới nhất do Payroll Administrator cung cấp.
- **Xóa nhân viên thành công:** Nhân viên được đánh dấu để xóa và sẽ được xóa hoàn toàn khỏi hệ thống sau khi phát lương cuối.
- **Thông báo lỗi:** Hệ thống hiển thị lỗi nếu ID nhân viên không tồn tại hoặc Payroll Administrator không có quyền truy cập cần thiết.
- **Xác nhận trước khi xóa:** Payroll Administrator được yêu cầu xác nhận trước khi xóa nhân viên khỏi hệ thống.

## 6. Phân tích ca sử dụng Run Payroll

### a. Xác định các lớp phân tích
- **Entity Classes:**
    - **Employee:** Chứa thông tin về nhân viên, bao gồm ID, tên, mức lương, phương thức thanh toán, các khoản khấu trừ, lợi ích và trạng thái (như đã xóa).
    - **Timecard:** Lưu trữ dữ liệu về số giờ làm việc hoặc thời gian làm việc của nhân viên trong kỳ thanh toán hiện tại.
    - **PayrollRecord:** Chứa dữ liệu về bảng lương, bao gồm số tiền thanh toán, khoản khấu trừ và thông tin kỳ thanh toán.
    - **BankTransaction:** Chứa thông tin giao dịch ngân hàng, bao gồm mã giao dịch, số tiền và trạng thái (như chờ xử lý).
     
- **Boundary Classes:**
  - **PayrollUI:** Giao diện cho Payroll Administrator để theo dõi và quản lý quá trình xử lý bảng lương, bao gồm các báo cáo về bảng lương và lịch sử thanh toán.
  - **BankSystemInterface:** Giao diện để hệ thống kết nối và gửi dữ liệu giao dịch đến hệ thống ngân hàng khi thanh toán qua chuyển khoản trực tiếp.
     
- **Control Classes:**
    - **PayrollController:** Điều khiển quá trình chạy bảng lương, bao gồm xác định thời gian chạy, truy xuất danh sách nhân viên cần thanh toán, tính toán tiền lương và thực hiện các phương thức thanh toán.
    - **BankTransactionController:** Quản lý quá trình gửi giao dịch đến hệ thống ngân hàng và xử lý các tình huống khi hệ thống ngân hàng không khả dụng.
### b. Biểu đồ tuần tự cho "Run Payroll"
![Diagram](https://www.planttext.com/api/plantuml/png/Z5JDZjCm4BxdAKOvxxv0fQ9jgy9M81IrEN0rZgcj9dP874JE7FQmfnuv81gg2l5JiH98ICbX3rdrFV84l09ZTnlQicYfr5ZrV3FppVTD-gkwFairINGMXGwXMYNWaJnHOTWB8Y55gXDYBaaANi-94IYeY8dKEzX0IMrEjiKC3Z33A0vLpfW93GyYleWO9KbW8lvTTSUCgctO6n_4-qJE_8J85DaA9GsYx_-5cEIfPj58QfQy8DGIw4z6ZjFjmcFULEy5tCoRwgsSmikiBa0dzLV9WVAcB79utfHBZ8IRgqs1PxVhU3quVO3JTOwptN4cTvHTnniOsB03JvfobKD0i6PQ5vI3vFK72Qz4_La2RSgF4ZGtKQtgGZgXKZ4yH9aPGIoxLSq1_6nB-ct9fle6eMYgYwpLS0_NjjQy_e7qj92xCKuWRAgbW7fD-GdCSD9LXdCtrHURRnyaHFtvxTWQ9_r4ztb2M2_0ZOW8NU2gANzIS6D1PwTPxDhyFqIySGTy55CT-da7QYGX9ZdbZCvib8Kfkvz48196DGGiLgdGnztx_gxxqRQqkBvlSPDH1nurrLh0L11brBr40z3Sybe2jhwm1EP8H4wDWRnUo6bRnCXr_WyGAcmTC48lJU7LNk8H0xHi7QCzPN788oMPBVtENajS8ZHDszsxbBojnkHMrztPMlbqR-bkvlKI7vihN09gVXKeQ62NmDHx0w_hx-H8HjocPtYxlxnj8_ErRnDAfSswbVG_NwMjyxqEd2iKogGk47zlhdE6BSs_r6y0003__mC0)

### c. Phân tích chức năng và dữ liệu
- **Employee:** Cung cấp dữ liệu nhân viên để tính toán lương và xác định phương thức thanh toán.
- **PayrollRecord:** Lưu lại thông tin về kỳ lương và các khoản thanh toán đã xử lý.
- **BankTransaction:** Quản lý các giao dịch ngân hàng cho các thanh toán qua "direct deposit", bao gồm cả trạng thái giao dịch.
- **PayrollUI:** Cung cấp giao diện cho Payroll Administrator để xem, theo dõi, và kiểm tra các báo cáo bảng lương.
- **PayrollController:** Thực hiện các quy trình xử lý bảng lương như lấy danh sách nhân viên, tính toán lương và lựa chọn phương thức thanh toán.
- **BankTransactionController:** Đảm bảo các giao dịch chuyển khoản được thực hiện và kiểm soát lỗi khi hệ thống ngân hàng không khả dụng.

### d. Kết quả mong đợi
- **Chạy bảng lương thành công:** Bảng lương được xử lý đúng lịch cho tất cả nhân viên đủ điều kiện.
- **In paycheck hoặc chuyển khoản thành công:** Paycheck được in nếu phương thức là "mail" hoặc "pick-up", và các giao dịch ngân hàng thành công nếu chọn "direct deposit".
- **Thông báo lỗi khi hệ thống ngân hàng không khả dụng:** Hệ thống sẽ tự động lập lại việc gửi giao dịch khi hệ thống ngân hàng khả dụng.
- **Xóa nhân viên đã đánh dấu:** Nhân viên được xóa khỏi hệ thống sau khi bảng lương đã xử lý.
- **Trạng thái hệ thống không đổi:** Không có thay đổi lớn sau khi xử lý bảng lương ngoài việc lưu trữ thông tin thanh toán.

# II. Mô phỏng ca sử dụng Maintain Timecard.

## 1. Lớp Employee
```java
    public class Employee {
    private String employeeId;
    private String name;

    public Employee(String employeeId, String name) {
        this.employeeId = employeeId;
        this.name = name;
    }

    public String getEmployeeId() {
        return employeeId;
    }

    public String getName() {
        return name;
    }
}

```
## 2. Lớp Timecard
```
import java.util.Date;

public class Timecard {
    private String employeeId;
    private Date date;
    private double hoursWorked;
    private String chargeCode;

    public Timecard(String employeeId, Date date, double hoursWorked, String chargeCode) {
        this.employeeId = employeeId;
        this.date = date;
        this.hoursWorked = hoursWorked;
        this.chargeCode = chargeCode;
    }

    public String getEmployeeId() {
        return employeeId;
    }

    public Date getDate() {
        return date;
    }

    public double getHoursWorked() {
        return hoursWorked;
    }

    public String getChargeCode() {
        return chargeCode;
    }
}
```
## 3. Lớp TimecardEntryUI
```
import java.util.Scanner;
import java.util.Date;

public class TimecardEntryUI {
    private Scanner scanner;

    public TimecardEntryUI() {
        scanner = new Scanner(System.in);
    }

    public Timecard getTimecardDetails(String employeeId) {
        System.out.println("Enter date (YYYY-MM-DD): ");
        Date date = new Date();  // Giả định ngày đã được định nghĩa hoặc người dùng sẽ nhập đúng định dạng này
        System.out.println("Enter hours worked: ");
        double hoursWorked = scanner.nextDouble();
        System.out.println("Enter charge code: ");
        String chargeCode = scanner.next();
        return new Timecard(employeeId, date, hoursWorked, chargeCode);
    }
}
```
## 4. Lớp TimecardController
```
import java.util.ArrayList;
import java.util.List;

public class TimecardController {
    private List<Timecard> timecards;

    public TimecardController() {
        timecards = new ArrayList<>();
    }

    public void submitTimecard(Employee employee, TimecardEntryUI ui) {
        Timecard timecard = ui.getTimecardDetails(employee.getEmployeeId());

        if (validateTimecard(timecard)) {
            timecards.add(timecard);
            System.out.println("Timecard submitted successfully for employee ID: " + employee.getEmployeeId());
        } else {
            System.out.println("Timecard validation failed. Please check the entered data.");
        }
    }

    private boolean validateTimecard(Timecard timecard) {
        return timecard.getHoursWorked() > 0 && timecard.getHoursWorked() <= 24;
    }

    public void displayTimecards() {
        for (Timecard timecard : timecards) {
            System.out.println("Employee ID: " + timecard.getEmployeeId() +
                               ", Date: " + timecard.getDate() +
                               ", Hours Worked: " + timecard.getHoursWorked() +
                               ", Charge Code: " + timecard.getChargeCode());
        }
    }
}
```
## 5. Lớp MaintainTimecardApp
```
public class MaintainTimecardApp {
    public static void main(String[] args) {
        Employee employee = new Employee("E001", "John Doe");
        TimecardEntryUI ui = new TimecardEntryUI();
        TimecardController controller = new TimecardController();

        controller.submitTimecard(employee, ui);
        controller.displayTimecards();
    }
}
```
