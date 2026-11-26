# Báo cáo Day 14 — Nguyễn Mạnh Dũng — 2A202603197

- Mã học viên dùng với `--student`: `197`
- `seed_tag` trong `frames_A.txt`: `393590736f`

## 1. Dự đoán trước sweep (bước 5b)

Ghi **trước** khi chạy `scripts/pp_sweep.py`, rồi commit và push ngay (lịch sử commit là bằng chứng thời điểm viết). Không sửa phần này sau khi có kết quả.

- Tham số tôi nghĩ giảm công sửa nhiều nhất: tăng `score_thr` từ 0.1 lên 0.4.
- Vì sao: Tôi dự đoán tăng `score_thr` từ 0.1 lên 0.4 sẽ giảm chi phí sửa. Ở cấu hình gốc, tập A có 60 box cần xóa, 2 box cần thêm và 14 box cần sửa, tổng chi phí là 27.0. Tôi kỳ vọng tăng ngưỡng tin cậy sẽ loại bớt box thừa và giảm thao tác xóa. Tuy nhiên, ngưỡng cao có thể loại cả box của vật thể thật, làm tăng số box phải thêm. Vì vậy, tôi dự đoán chi phí sẽ giảm nhưng cần kiểm chứng bằng sweep.

## 2. Tập A: sửa tay và tune

| Cấu hình | Xóa | Thêm | Sửa | Chi phí |
|---|---:|---:|---:|---:|
| Gốc | 60 | 2 | 14 | 27.0 |
| `best_config.json` | | | | |

- Tham số đã đổi trong `best_config.json`: ...
- Kết quả leave-one-out (dán các dòng `scripts/pp_sweep.py` in ra): ...
- Cấu hình có ổn định trên từng frame không? Vì sao tôi vẫn chọn (hoặc không chọn) nó: ...

## 3. Trước/sau (bước 8)

![so sánh](../../d14_<ID>/compare/<frame>.jpg)

- `scripts/pp_compare.py` báo giảm (hoặc tăng) ...% công sửa trên tập A.
- Dự đoán ở mục 1 đúng hay sai? Giải thích bằng số box xóa/thêm/sửa: ...

## 4. Tập B

Số đo từ `scripts/pp_prelabel.py --frames d14_<ID>/frames_B.txt --config d14_<ID>/best_config.json --gt d14_<ID>/ref_B.json`:

| Xóa | Thêm | Sửa | Chi phí |
|---:|---:|---:|---:|
| | | | |

- Loại box tốn công sửa nhất ở tập B: ...

## 5. Giới hạn

- Nêu ít nhất 2 giới hạn (ví dụ: chỉ 3 frame tune; model KITTI không có Truck/Bus; chi phí là công thức, chưa phải thời gian sửa thật): ...
