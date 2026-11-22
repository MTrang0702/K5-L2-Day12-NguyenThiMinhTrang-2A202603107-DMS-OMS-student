# TEAM — Ngày 12

Mã bộ ảnh: **G04** · Hình thức: cá nhân

| Họ tên | MSSV | Đã gán đủ 22 ảnh? | Review chéo với (peer diff) | Số dòng disagreement đã xử lý |
|---|---|---|---|---|
| Nguyễn Thị Minh Trang | 2A202603107 | có | Lê Hoàng Nam (G04) | 9 dòng |

Ca hai bạn vẫn không thống nhất và đã hỏi coach (ghi tên ảnh + đối tượng):

- `S01_rgb.png`: Vấn đề hình ma-nơ-canh trẻ em ngồi trong ghế an toàn trẻ em (`child_seat`). Hai bạn thảo luận có nên gán thêm box `object` hay không. Coach đã giải thích: Guideline quy định "Thấy hình giống trẻ em thì báo coach, không gán", vì vậy chỉ gán box `child_seat` với thuộc tính `occupied=unknown` và không vẽ box thêm cho ma-nơ-canh.

## Cá nhân

### NguyenThiMinhTrang-2A202603107
- Phần mình làm: Tự gán toàn bộ 22 ảnh (16 ảnh OMS và 6 ảnh DMS), xuất file và chạy kiểm tra tự động `cabin_check.py`, đối chiếu diff với bạn Lê Hoàng Nam và ghi nhận nhật ký bất đồng.
- Điều mình học được hôm nay:
  1. Hiểu sâu sắc hệ quy chiếu trong gán nhãn xe hơi: ghế gọi theo chiều xe chạy, mắt/tay gọi theo cơ thể người.
  2. Sự khác biệt giữa ảnh hồng ngoại thực tế (NIR của Drive&Act) với ảnh mô phỏng hồng ngoại (IR-sim của SVIRO).
  3. Kỹ năng gán nhãn skeleton 13 điểm mốc mặt khi ảnh bị xoay 90 độ và xử lý cờ occluded/outside cho các điểm bị che khuất.
