# Tự đánh giá — Nguyễn Thị Minh Trang · G04

## 1. Tự rà soát 4 cảnh

Nghỉ tay 1 phút, mở lại bài của mình, chọn 4 ảnh (2 S##, 2 D##), đọc như người lạ.

Loại lỗi: `seat_flip`, `wrong_class`, `guess`, `box`, `missing`, `extra`, `lr_flip` (trái/phải mặt), `flag` (thiếu cờ điểm), `ok`.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| `S01_rgb.png` | `child_seat` (bên trái ảnh) | `ok` | Ghế bên trái gán đúng `seat=rear_right` theo xe; bên trong có búp bê trẻ em để `occupied=unknown` | Rồi |
| `S03_ir.png` | `object` (ghế giữa) | `ok` | Nhìn rõ cốc có quai trên ảnh IR-sim, gán `type=cup`, `seat=rear_middle` | Rồi |
| `D01.png` | `face13` | `ok` | Mặt nghiêng làm mắt trái bị che; các điểm `left_eye_*` bật cờ `occluded=1`; mắt trái có y lớn hơn mắt phải | Rồi |
| `D04.png` | `phone` & `hand` | `ok` | Vẽ đủ box `phone` (held) và `hand` (whose=driver, side=left) áp tai; tay phải để on_wheel=no | Rồi |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

- **Lỗi:** Xu hướng gán trái/phải theo góc nhìn của màn hình (camera) thay vì gọi theo xe (OMS) và gọi theo người (DMS).
- **Vì sao mình mắc:** Theo thói quen thị giác tự nhiên, khi nhìn vào màn hình rất dễ gọi bên trái ảnh là ghế trái (`rear_left`) hoặc mắt bên trái ảnh là mắt trái.
- **Lần sau tránh bằng cách:** 
  1. Với OMS: Tưởng tượng mình đang ngồi quay mặt về phía trước xe (camera sau lưng nhìn ngược lại), bên trái ảnh luôn là ghế phải của xe (`rear_right`).
  2. Với DMS: Ảnh Drive&Act xoay 90°, luôn nhớ trục y là trục mắt: mắt trái của người luôn có tung độ y lớn hơn mắt phải.

## 3. Ghi chú về disagreement_log

Một dòng bạn của mình đúng và mình sai. Mình học được gì từ dòng đó:
- Ở ảnh `D06.png`, ban đầu mình định gán `seatbelt=not_worn` vì thấy chốt khóa chưa gài vào ổ. Tuy nhiên, sau khi thảo luận và đối chiếu guideline mục 4.7 ("unknown: không thấy, bị che, đang thắt dở"), bạn chỉ ra rằng tài xế đang dùng hai tay cầm chốt thao tác cài dây (đang thắt dở) nên chuẩn xác nhất phải là `unknown`. Mình đã hiểu rõ hơn nguyên tắc không đoán trạng thái cuối khi thao tác đang diễn ra.
