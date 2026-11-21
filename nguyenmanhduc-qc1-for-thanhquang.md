# Phiếu QC 1 — Road v1.0

**Lô được kiểm** Nguyễn Thanh Quang · **Người kiểm** Nguyễn Mạnh Đức  
**Ngày kiểm lại** 21/11/2026 · **Guideline** Road v1.0  
**File được kiểm** `thanhquang-front.zip` và `thanhquang-fisheye.zip`. **Revision của cả lô chưa xác định.** Manifest `thanhquang-manifest-r1.json` ghi revision 1. SHA-256 khớp với ZIP fisheye, còn ZIP front hiện tại có SHA-256 khác.  
**Giờ export theo XML (giờ Việt Nam)** front 22:21:07, fisheye 22:27:13 ngày 20/11/2026.

**Mẫu kiểm** A05, A06, A08, A09, B06 và B07 (4 front, 2 fisheye, 0 ảnh thêm). **Số nhãn đã kiểm** 88 (64 shape và 24 tag). Lần này đối chiếu XML mới với các lỗi và ca mơ hồ đã ghi khi xem ảnh gốc.

## Tổng hợp theo mã

Số lỗi trong bảng chỉ gồm lỗi đã xác nhận trên mẫu. Các cảnh báo cần đối chiếu được ghi ở mục Ca mơ hồ.

| Mã | Loại lỗi | Số mục kiểm | Số lỗi xác nhận | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 | Tag camera và tag ảnh | 24 tag | 0 | nặng / nhẹ |
| QC1-02 | Đủ L1, R1 | 8 vị trí trên 4 ảnh front | 0 | nặng |
| QC1-03 | Position | 13 lane | 0 | nặng |
| QC1-04 | Tâm vạch, chiều, điểm dừng | 13 lane | 0 | chính |
| QC1-05 | Vạch đứt, che | 13 lane | 0 | chính |
| QC1-06 | Style, color, kind | 13 lane | 0 | chính |
| QC1-07 | Vùng lái, crosswalk, road_curb | 28 shape | 0 | chính |
| QC1-08 | Đèn, màu | 13 box đèn | 0 | nặng / chính |
| QC1-09 | Facing, type, group, biển phụ | 23 box | 0 | chính |
| QC1-10 | Hình in, đủ biển | 10 box biển | 0 | chính |
| QC1-11 | Fisheye | 9 polyline | 0 | chính |
| QC1-12 | File | 2 ZIP | 0 trong phạm vi mở file | nhẹ / nặng |

## Danh sách lỗi đã xác minh

Các lỗi đã ghi trong phiếu trước đã được sửa trong hai ZIP hiện tại. Sáu ảnh mẫu có đủ tag, A09 đã đổi vạch đứt sang `R1` và gộp vạch đôi thành một `L1`, các lane B06–B07 đã chuyển sang `other`, và sáu box đèn ghi sai màu ở A06–A08 đã chuyển sang `green`.

## Ca mơ hồ

| Ảnh | Câu hỏi cần xác nhận | Lời đáp |
| --- | --- | --- |
| A05 | Không thấy rõ vạch sơn phân làn. Xác nhận để trống L1 và R1? | Chờ coach |
| A06 | Không thấy rõ vạch sơn phía phải làn. Xác nhận để trống R1? | Chờ coach |
| A08 | Xác nhận lane #10 có phải L1 và lane #25 có phải vạch dừng? Nếu #25 là vạch dừng thì bỏ nhãn lane. | Chờ đối chiếu |
| B06, B07 | Kiểm tra độ bám cung của road_curb #4 (B06) và lane #4, #5 (B07) trên ảnh phóng to. | Chờ đối chiếu |

## Quyết định

**Hold.** Kết quả theo các lỗi đã xác nhận trên mẫu là **0 nặng**, **0 lỗi chính / 88 nhãn = 0%** và **0 nhẹ**. Cần xác nhận các ca ở trên trước khi kết luận Release.

Lint toàn lô giảm từ **12 xuống 10 cảnh báo** trên 20 ảnh. Năm cảnh báo QC1-02 gồm A05 (L1 và R1), A06 (R1), A07 (L1) và A12 (L1). Năm cảnh báo chính là một cảnh báo chiều vẽ ở A08 và bốn gợi ý rà độ bám cung ở B03, B06, B07. A07, A12 và B03 nằm ngoài mẫu sáu ảnh.

