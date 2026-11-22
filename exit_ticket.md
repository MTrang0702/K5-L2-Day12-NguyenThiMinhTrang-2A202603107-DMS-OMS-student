# Exit ticket — Ngày 12

Làm cá nhân, không mở slide, khoảng 10 phút. Ghi đáp án ngay dưới mỗi câu.

**Họ tên:** Nguyễn Thị Minh Trang · **Mã:** G04

---

**Câu 1 · Chọn một.** Camera DMS trên nhiều xe tự chiếu đèn LED cận hồng ngoại khoảng 940 nm lên mặt tài xế. Lý do chính là gì?

- A. Để đo nhiệt độ da và phát hiện tài xế bị sốt
- B. Để có ảnh mặt ổn định cả ngày lẫn đêm mà không làm chói mắt tài xế
- C. Để có ảnh màu đẹp hơn cho cuộc gọi video
- D. Để camera nhìn xuyên qua mọi loại kính râm

Đáp án: B

*Giải thích:* Đèn LED NIR bước sóng 940 nm nằm ngoài dải phổ ánh sáng khả kiến mà mắt người có thể cảm nhận được nên không làm chói mắt tài xế khi lái xe ban đêm, đồng thời cung cấp nguồn sáng chủ động ổn định 24/7 cho camera cabin.

---

**Câu 2 · Số, 2 chữ số thập phân.** Camera DMS chạy 30 khung hình/giây. Model ước lượng yaw của đầu tài xế lớn hơn 30° liên tục từ khung hình số 240 đến khung hình số 314, **tính cả khung 240 và khung 314**. Tài xế không nhìn đường trong bao nhiêu giây?

Đáp án: 2.50 s

*Cách tính:*  
- Tổng số khung hình = 314 - 240 + 1 = 75 khung hình.  
- Thời gian = 75 / 30 = 2.50 giây.

---

**Câu 3 · Chọn tất cả đáp án đúng.** Những câu nào đúng về dữ liệu cabin so với dữ liệu camera ngoài xe?

- A. Không thể làm mờ mặt tài xế như làm mờ mặt người qua đường, vì model DMS cần chính khuôn mặt.
- B. Ban đêm, ảnh cabin thường là ảnh hồng ngoại đen trắng, nên thuộc tính màu áo không gán được.
- C. Camera OMS nhìn về phía sau xe, nên ghế ở bên trái ảnh là ghế bên phải của xe.
- D. Vật trong cabin thường ở xa và nhỏ, nhiều vật trong một ảnh.
- E. Cảnh cabin cố định nên không cần guideline hay QC riêng.

Đáp án: A, B, C

*Giải thích:*  
- A đúng: DMS cần đặc trưng mắt, mũi, miệng để phát hiện buồn ngủ và tư thế đầu nên không thể làm mờ mặt.  
- B đúng: Ảnh NIR là ảnh đơn sắc (grayscale theo độ phản xạ hồng ngoại), mất thông tin màu sắc RGB.  
- C đúng: Camera nhìn ngược chiều xe (từ trước ra sau) nên bên trái ảnh tương ứng với bên phải của xe (`rear_right`).  
- D sai vì trong cabin khoảng cách camera rất gần (gần và lớn).  
- E sai vì cabin có nhiều trường hợp che khuất phức tạp và yêu cầu an toàn cao nên rất cần guideline và QC nghiêm ngặt.
