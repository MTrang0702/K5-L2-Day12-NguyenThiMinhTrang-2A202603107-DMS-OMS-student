# Danh sách lớp v0 — DMS & OMS (G04)

Danh sách lớp và thuộc tính cabin v0 xây dựng theo Guideline Cabin v1.0 và slide 40–54 bài giảng. Mỗi lớp mô tả mục đích chức năng và khả năng nhận biết trên ảnh hồng ngoại (NIR/IR).

## DMS (Hệ thống giám sát người lái - Driver Monitoring System)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `eye_state` (`eye_left`, `eye_right`) | `open` / `closed` / `unknown` | Phát hiện buồn ngủ (Drowsiness Detection) dựa trên tỷ lệ nhắm mắt (PERCLOS) và tần suất chớp mắt bất thường | Có, NIR 850/940 nm xuyên qua bóng tối; chỉ bị cản bởi kính râm tối đặc hoặc đốm lóa phản xạ cực mạnh |
| 2 | `gaze_zone` | `road`, `mirror_l`, `mirror_r`, `mirror_c`, `cluster`, `center`, `lap`, `other` | Phát hiện mất tập trung thị giác (Visual Distraction): cảnh báo khi mắt rời khỏi đường (road/mirrors) quá 2 giây liên tục | Có, nhìn rõ đồng tử và hướng đầu (head pose) dưới ánh sáng NIR trong cabin |
| 3 | `glasses` | `none` / `clear` / `sun` / `unknown` | Điều chỉnh thuật toán nhận diện mắt và trắc lượng đồng tử phù hợp với từng loại phụ kiện quang học | Có, phân biệt được kính mắt cận (clear) và mắt thường; tuy nhiên kính râm phân cực có thể trong suốt hơn trên NIR |
| 4 | `face13` (13 điểm mốc mặt) | 13 keypoints (mắt, mũi, miệng) | Ước lượng tư thế đầu 3D (Head Pose Estimation 6-DoF) và độ mở miệng (phát hiện ngáp - Yawning Detection) | Có, các mốc giải phẫu khuôn mặt phản xạ đồng đều dưới đèn LED hồng ngoại |
| 5 | `hand.on_wheel` | `yes` / `no` / `unknown` | Giám sát tay trên vô lăng (Hands-On Detection - HOD) cho xe tự hành cấp độ 2/3 (L2/L3 handover) | Có, độ tương phản giữa da bàn tay và vô lăng hiển thị rõ ràng trên ảnh hồng ngoại |
| 6 | `phone.state` | `held` / `mounted` / `lap` | Phát hiện hành vi sử dụng điện thoại khi lái xe (Phone Distraction Detection) để cảnh báo an toàn và phạt vi phạm | Có, nhận diện qua hình dạng viền chữ nhật, góc bo và độ tương phản vật liệu kính/kim loại của điện thoại |
| 7 | `person.seatbelt` | `worn_correct` / `worn_incorrect` / `not_worn` / `unknown` | Kiểm tra thắt dây an toàn của tài xế và nhận diện thắt sai cách (dưới nách/sau lưng) để kích hoạt cảnh báo âm thanh | Có, dải dây an toàn phản xạ khác biệt so với chất liệu vải áo dưới ánh sáng NIR |

## OMS (Hệ thống giám sát hành khách & khoang xe - Occupant Monitoring System)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person` (người lớn) | `seat`: driver, front_passenger, rear_left, rear_middle, rear_right | Nhận biết có người ngồi theo từng ghế để kích hoạt bung túi khí thông minh và nhắc nhở thắt dây an toàn | Có, phân biệt rõ hình dạng cơ thể người so với ghế trống |
| 2 | `child_seat` (ghế trẻ em) | `seat`: rear_left, rear_middle, rear_right; `occupied`: `no` / `unknown` | Tùy chỉnh chế độ bung túi khí ghế phụ hoặc nhắc kiểm tra ghế trẻ em khi rời xe | Có, nhận diện rõ cấu trúc hình học ghế trẻ em (booster, lưng đỡ cao) |
| 3 | `infant_seat` (nôi em bé) | `seat`: rear_left, rear_middle, rear_right; `facing`: `rear` / `front` | TẮT BẮT BUỘC túi khí phía trước nếu nôi quay về sau (`rear`) nhằm tránh chấn thương tử vong cho trẻ khi va chạm | Có, thấy rõ tay xách, góc nghiêng lòng nôi và hướng quay của nôi xách |
| 4 | `object` (loại `bag` / `box` / `cup`) | `seat`: theo vị trí ghế; `type`: `bag` / `box` / `cup` / `other` | Cảnh báo đồ vật để quên trong xe (Left-behind Object Warning) và tránh nhầm lẫn đồ vật với người ngồi để không bung túi khí giả | Có, nhận biết bằng hình dáng khối hộp, quai túi hoặc thành cốc |
| 5 | `frame_meta.camera_blocked` | `yes` / `no` | Phát hiện lỗi cảm biến, ống kính camera bị che khuất hoặc bụi mờ bám để yêu cầu bảo trì hệ thống an toàn | Có, ảnh bị mờ hoàn toàn hoặc đen đặc khi ống kính bị che |
| 6 | `person.seatbelt` | `worn_correct` / `worn_incorrect` / `not_worn` / `unknown` | Nhắc nhở thắt dây an toàn cho từng vị trí hành khách hàng ghế sau (Seatbelt Reminder System - SBR) | Khá khó nếu áo tối màu trên IR; cần dựa vào độ phản xạ của chất liệu dải dây an toàn |

## 2 câu hỏi leo thang (Escalation Questions)

1. **Câu hỏi:** Trong các khung hình S01 và S03, ghế an toàn trẻ em (`child_seat`) và nôi em bé (`infant_seat`) có ma-nơ-canh / búp bê hình trẻ em bên trong. Guideline v1.0 ghi *"Bộ ảnh không có trẻ em ngồi. Thấy hình giống trẻ em thì báo coach, không gán."* Vậy đối với ma-nơ-canh trẻ em này, chúng ta có gán nhãn `object` (loại `other`) nằm trong ghế trẻ em không, hay hoàn toàn bỏ qua không vẽ box cho hình trẻ em?  
   - **Khung ví dụ:** `S01_rgb.png` (ghế `rear_right`), `S03_ir.png` (ghế `rear_right` và `rear_left`).  
   - **Tạm gán và lý do:** Tuân thủ đúng nguyên tắc *"Thấy hình giống trẻ em thì không gán"*, ta không vẽ box `person` và cũng không vẽ box `object` cho búp bê trẻ em. Thay vào đó, vẽ box `child_seat` / `infant_seat` bao quanh cả ghế với thuộc tính `occupied = unknown` (do bên trong có vật thể chiếm chỗ nhưng không phải hành khách người lớn).

2. **Câu hỏi:** Trong khung hình `D06.png`, tài xế đang dùng hai tay cầm và cài chốt dây an toàn (thao tác đang diễn ra, chưa cài xong vào chốt). Thuộc tính `seatbelt` nên được gán là `not_worn` (vì chốt chưa khóa) hay `unknown` (vì đang thắt dở)?  
   - **Khung ví dụ:** `D06.png`.  
   - **Tạm gán và lý do:** Guideline mục 4.7 quy định: *"unknown: không thấy (tối, bị che, đang thắt dở)"*. Do đó, tạm gán `seatbelt = unknown` cho D06 để phản ánh chính xác trạng thái đang thao tác chuyển đổi hành vi, tránh dạy model nhận diện sai giữa việc không thắt với đang chuẩn bị thắt.
