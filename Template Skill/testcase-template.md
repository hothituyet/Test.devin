# DEVIN INSTRUCTIONS: GENERATE TEST CASES

Khi tôi yêu cầu sinh Test Case cho một file tài liệu, hãy đóng vai một **Senior QA/Test Engineer** và thực hiện theo đúng các quy định sau:

### 1. NGUYÊN TẮC PHÂN TÍCH TÀI LIỆU
- Phân tích kỹ các luồng nghiệp vụ (Business Rules), điều kiện ràng buộc (Constraints), và giao diện (UI/UX) được mô tả trong tài liệu đầu vào.
- Suy nghĩ từng bước để tóm tắt và phân tích dễ hiểu thông tin trong tài liệu.
  Bước 1: Tạo một danh sách các tính năng của app
  Bước 2: Với mỗi tính năng, đặt câu hỏi xác minh về chức năng nhằm mục đích gì, giải quyết vấn đề gì cho khách hàng, cách khách hàng có thể sử dụng tính năng đó như thế nào, làm sao có thể kiểm tra tính năng đó đã đúng với requirement đã viết ở trong tệp đính kèm.
  Bước 3: Trả lời từng câu hỏi xác minh.
  Bước 4: Dựa trên kết quả xác minh, lọc danh sách và đưa ra phản hồi cuối cùng.
  Bước 5: Tạo kết quả tóm tắt bổ sung vào đầu file test cases, hãy thêm 1 mục:
  `### 📌 Tóm tắt tài liệu`

- Bao phủ đầy đủ các nhóm kịch bản:
  1. **Positive / Happy Path:** Luồng thực thi chuẩn khi nhập đúng dữ liệu.
  2. **Negative / Error Handling:** Nhập sai dữ liệu, để trống field bắt buộc, vượt giới hạn độ dài, sai định dạng.
  3. **Boundary Value & Edge Cases:** Kiểm tra giá trị biên (Min, Max, cận trên, cận dưới), ký tự đặc biệt, XSS/SQL Injection cơ bản.
  4. **State & Authorization:** Phân quyền người dùng (User/Admin) và trạng thái hệ thống trước/sau khi thực hiện.

---

### 2. QUY CÁCH TẠO FILE ĐẦU RA (OUTPUT)
- **Địa điểm lưu file:** Tự động tạo file kết quả nằm trong thư mục `test-cases/` (Ví dụ: `test-cases/TC_TênTínhNăng.md`).
- **Định dạng:** Trình bày dạng **Bảng Markdown** chuẩn với cấu trúc cột sau:

| Test Case ID | Kịch bản Test (Scenario) | Điều kiện tiên quyết (Pre-conditions) | Các bước thực hiện (Test Steps) | Dữ liệu Test (Test Data) | Kết quả mong đợi (Expected Result) | Loại Test (Type) | Độ ưu tiên (Priority) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |

#### Quy tắc điền dữ liệu:
- **Test Case ID:** Đặt theo chuẩn `TC_[MãTínhNăng]_[STT]` (Ví dụ: `TC_AUTH_001`).
- **Các bước thực hiện:** Ghi chi tiết từng bước dạng `1. ... \n 2. ... \n 3. ...`.
- **Loại Test (Type):** Đánh dấu rõ `Positive`, `Negative`, `Boundary`, hoặc `Security`.
- **Độ ưu tiên (Priority):** Đánh dấu `High`, `Medium`, hoặc `Low`.

---

### 3. BỔ SUNG GHI CHÚ
Ở cuối file Test Case vừa tạo, hãy thêm một mục:
`### 📌 Lời khuyên & Ghi chú cho QA`
Nêu rõ các điểm mâu thuẫn/chưa rõ ràng (ambiguity) hoặc rủi ro tiềm ẩn mà bạn phát hiện được trong tài liệu yêu cầu.