# 1. **BankSystem::deposit**

## 1.1 **Xác định lớp và thuộc tính**

- **`BankSystem`**: Đại diện cho hệ thống ngân hàng quản lý các giao dịch.
- **`BankTransaction`**: Xử lý các giao dịch tiền gửi.
- **`Paycheck`**: Đại diện cho bảng lương nhân viên với các thông tin về số tiền lương.
- **`BankInformation`**: Thông tin về ngân hàng như tên ngân hàng và số định tuyến.

## 1.2 **Xác định phương thức**

- **`BankSystem.deposit(Paycheck, BankInformation)`**
- **`BankTransaction.create(op, amount, routingNum)`**
- **`BankTransaction.submit()`**

## 1.3 **Class Diagram**

![BankSystem Class Diagram](https://www.planttext.com/api/plantuml/png/T951Ri8m44NtFiKiGKeka0L2NLHYWoh11IREj8s8FP5dl8WG9sF1aRW22Ks20TNBxpzl_hUlvyjQ58D6rnZRe0Xye3_iEb5oS3HmFnMrBBKklh2plsGFsTsqyTyS76hDVcbE9XdV1_I2ThYP6JOGAYsuBM2deVO_6Q3ZwBM0puPHCmWSjTUtqKsMvJWhiNJz-cJBb6J4vy-iKIFNDjmHRQe9-1mpAJ1pobxVegDvuaz-P2iffBJajV9yzTQ-W2WavbKUh7E50jh0bkG_uslKaRacNms_TWC00F__0m00)

## 1.4 **Biểu Đồ Trạng Thái**

- Các trạng thái của giao dịch:
  - **Khởi tạo** → **Đang xử lý** → **Hoàn tất**

![BankSystem State Diagram](https://www.planttext.com/api/plantuml/png/T951Ri8m44NtFiKiGKeka0L2NLHYWoh11IREj8s8FP5dl8WG9sF1aRW22Ks20TNBxpzl_hUlvyjQ58D6rnZRe0Xye3_iEb5oS3HmFnMrBBKklh2plsGFsTsqyTyS76hDVcbE9XdV1_I2ThYP6JOGAYsuBM2deVO_6Q3ZwBM0puPHCmWSjTUtqKsMvJWhiNJz-cJBb6J4vy-iKIFNDjmHRQe9-1mpAJ1pobxVegDvuaz-P2iffBJajV9yzTQ-W2WavbKUh7E50jh0bkG_uslKaRacNms_TWC00F__0m00)

---

# 2. **PrintService::print**

## 2.1 **Xác định lớp và thuộc tính**

- **`PrintService`**: Quản lý việc in bảng lương.
- **`PaycheckPrinterImage`**: Tạo hình ảnh in từ bảng lương.
- **`PrinterInterface`**: Giao tiếp với máy in.
- **`Employee`**: Lưu thông tin nhân viên.

## 2.2 **Xác định phương thức**

- **`PrintService.print(Paycheck, String)`**
- **`PaycheckPrinterImage.buildPrintImage(fromPaycheck)`**

## 2.3 **Class Diagram**

![PrintService Class Diagram](https://www.planttext.com/api/plantuml/png/T951Ri8m44NtFiKiGKeka0L2NLHYWoh11IREj8s8FP5dl8WG9sF1aRW22Ks20TNBxpzl_hUlvyjQ58D6rnZRe0Xye3_iEb5oS3HmFnMrBBKklh2plsGFsTsqyTyS76hDVcbE9XdV1_I2ThYP6JOGAYsuBM2deVO_6Q3ZwBM0puPHCmWSjTUtqKsMvJWhiNJz-cJBb6J4vy-iKIFNDjmHRQe9-1mpAJ1pobxVegDvuaz-P2iffBJajV9yzTQ-W2WavbKUh7E50jh0bkG_uslKaRacNms_TWC00F__0m00)

## 2.4 **Biểu Đồ Trạng Thái**

- Các trạng thái của quá trình in:
  - **Chuẩn bị in** → **Đang in** → **Hoàn thành**

![PrintService State Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3XUGKPAge1HGb5gGM9IPbwwaa5Yi0E8XP3BpIX0IG0vCnZa_jo0djIGr1Ipbaf-NoiKLhHMheAjh1p41H41vG6qALWh1gNaf2YNv2WKWVceH5qGSf0Aa6wZ0BJClipW38W-qayi1g07aIW00003__mC0)

---

# 3. **ProjectManagementDatabase::getChargeNumbers**

## 3.1 **Xác định lớp và thuộc tính**

- **`ProjectManagementDatabase`**: Quản lý cơ sở dữ liệu dự án.
- **`ChargeNumList`**: Danh sách số tính phí.
- **`ChargeNum`**: Đại diện số tính phí với thông tin dự án.

## 3.2 **Xác định phương thức**

- **`getChargeNumbers(String)`**
- **`ChargeNumList.add(theChargeNum)`**

## 3.3 **Class Diagram**

![ProjectManagementDatabase Class Diagram](https://www.planttext.com/api/plantuml/png/T51B2i8m4Dtd55dQHI_GXHGKGT0YU89fCiHAaafcuaOycGkFv1MiDIrMT9RlEpEFsxqaXi3HMQ4i4CbTQ8-eU0iU33hql0I66WZbHSX-3FBY0C5W5LsDWMQdjsMj2xddq7YJ5N9KR1fYSHKfVGAFYQ3rJ0tCXpVxOKocNARM2XmElOavWuqTjh8jzDN_Jyhp-TTAXGp8CNWIKtoYx5IgzGnD9olHwzVtdW000F__0m00)

## 3.4 **Biểu Đồ Trạng Thái**

- Các trạng thái của danh sách số tính phí:
  - **Rỗng** → **Đang cập nhật** → **Hoàn tất**

![ProjectManagementDatabase State Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3XUGKPAgeEIQMr1IgQIGMAm0Pi64GmjI4aioyzB1CZ0EJD8vFxSW9xKaDGKi2-TnSKLhnIhewjf1ZGAJO3xC00Kh1SUK58NaZCIYz5I5lDBSfDIYOYwuB4Wft3IWMhVClCpY38LIa7mgbqDgNWh8uG00003__mC0)

---

# 4. **ProjectManagementDatabase::initialize**

## 4.1 **Xác định lớp và thuộc tính**

- **`DBChargeNumbers`**: Kết nối cơ sở dữ liệu số tính phí.
- **`DriverManager`**: Quản lý và tạo kết nối cơ sở dữ liệu.

## 4.2 **Xác định phương thức**

- **`initialize()`**
- **`getConnection(url, user, pass)`**

## 4.3 **Class Diagram**

![Initialize Class Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niOABatD6Ob5wgbzfRb9gKR52DPS266JcPPPa9kPaLgLgQ7BLSi5K5sMMfHRv9kObfgSMmTMcfvOuv-VbfIQNPERdQPGMvLWf19SKPUQbwoYK5gSM8NW5G3DWFB2fwBRhwjgXsM45CgAOoo4rBmNaQ000003__mC0)

## 4.4 **Biểu Đồ Trạng Thái**

- Các trạng thái của kết nối cơ sở dữ liệu:
  - **Chưa kết nối** → **Đang kết nối** → **Kết nối thành công**

![Initialize State Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3XUGKPAgeEIIMPoSdvUNcboIcgAaa5YiW2m0K-GC4SZCImShGN3H542DWFEukAArOXLqTUrGJKNcW6KH1YfOAJWdvkGePEPbbcGcvcHMfN8XIIAf1UgqWklBprCeBarEJYqkJYlDuN98pKi1-H00003__mC0)
