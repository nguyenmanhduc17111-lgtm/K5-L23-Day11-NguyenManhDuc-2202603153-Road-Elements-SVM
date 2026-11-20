# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên) **Thanh Quang** · Người kiểm **Nguyễn Mạnh Đức**  
Ngày **20/11/2026** · Phiên bản guideline **Road v1.0**  
File được kiểm `thanhquang-front.zip` và `thanhquang-fisheye.zip`. Không có manifest đi kèm để xác định revision.  
Mẫu **A05, A06, A08, A09, B06, B07** (4 front, 2 fisheye, 0 ảnh thêm). Đã đối chiếu ảnh gốc với lớp nhãn chồng lên ảnh. Mẫu số tính tỉ lệ lỗi chính **65 nhãn hiện có** (65 shape, 0 tag). Các tag bị thiếu được ghi lỗi riêng.

## Tổng hợp theo mã

Số lỗi gồm các lỗi xác nhận được từ ảnh và XML. Mỗi nhãn có thể được kiểm theo nhiều mã. Các ca cần xác nhận được ghi bên dưới.

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 | Tag | 24 vị trí tag | 24 | nặng / nhẹ |
| QC1-02 | Đủ L1, R1 | 8 vị trí trên 4 ảnh front | 0 xác nhận riêng | nặng |
| QC1-03 | Position | 14 lane | 5 | nặng |
| QC1-04 | Tâm vạch, chiều, điểm dừng | 14 lane | 0 xác nhận riêng | chính |
| QC1-05 | Vạch đứt, che | 14 lane | 0 xác nhận | chính |
| QC1-06 | Style, color, kind | 14 lane | 2 | chính |
| QC1-07 | Vùng lái, crosswalk, road_curb | 28 shape | 0 xác nhận | chính |
| QC1-08 | Đèn, màu | 13 box đèn | 6 | nặng / chính |
| QC1-09 | Facing, type, group, biển phụ | 23 box | 0 xác nhận | chính |
| QC1-10 | Hình in, đủ biển | 10 box biển | 0 xác nhận | chính |
| QC1-11 | Fisheye | 9 polyline | 0 xác nhận | chính |
| QC1-12 | File | 2 ZIP (mở được) | 0 trong phạm vi mở file | nhẹ / nặng |

## Danh sách lỗi đã xác minh

| # | Mã | Ảnh | Nhãn | Mức | Mô tả |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-01 | A05 | camera | nặng | Thiếu tag camera. Giá trị cần gán là `front`. |
| 2 | QC1-01 | A05 | timeofday | nhẹ | Thiếu tag ảnh. |
| 3 | QC1-01 | A05 | weather | nhẹ | Thiếu tag ảnh. |
| 4 | QC1-01 | A05 | source | nhẹ | Thiếu tag ảnh. |
| 5 | QC1-01 | A06 | camera | nặng | Thiếu tag camera. Giá trị cần gán là `front`. |
| 6 | QC1-01 | A06 | timeofday | nhẹ | Thiếu tag ảnh. |
| 7 | QC1-01 | A06 | weather | nhẹ | Thiếu tag ảnh. |
| 8 | QC1-01 | A06 | source | nhẹ | Thiếu tag ảnh. |
| 9 | QC1-01 | A08 | camera | nặng | Thiếu tag camera. Giá trị cần gán là `front`. |
| 10 | QC1-01 | A08 | timeofday | nhẹ | Thiếu tag ảnh. |
| 11 | QC1-01 | A08 | weather | nhẹ | Thiếu tag ảnh. |
| 12 | QC1-01 | A08 | source | nhẹ | Thiếu tag ảnh. |
| 13 | QC1-01 | A09 | camera | nặng | Thiếu tag camera. Giá trị cần gán là `front`. |
| 14 | QC1-01 | A09 | timeofday | nhẹ | Thiếu tag ảnh. |
| 15 | QC1-01 | A09 | weather | nhẹ | Thiếu tag ảnh. |
| 16 | QC1-01 | A09 | source | nhẹ | Thiếu tag ảnh. |
| 17 | QC1-01 | B06 | camera | nặng | Thiếu tag camera. Giá trị cần gán là `fisheye_left`. |
| 18 | QC1-01 | B06 | timeofday | nhẹ | Thiếu tag ảnh. |
| 19 | QC1-01 | B06 | weather | nhẹ | Thiếu tag ảnh. |
| 20 | QC1-01 | B06 | source | nhẹ | Thiếu tag ảnh. |
| 21 | QC1-01 | B07 | camera | nặng | Thiếu tag camera. Giá trị cần gán là `fisheye_right`. |
| 22 | QC1-01 | B07 | timeofday | nhẹ | Thiếu tag ảnh. |
| 23 | QC1-01 | B07 | weather | nhẹ | Thiếu tag ảnh. |
| 24 | QC1-01 | B07 | source | nhẹ | Thiếu tag ảnh. |
| 25 | QC1-03 | B06 | lane #4 | nặng | Camera bên yêu cầu `position = other`. |
| 26 | QC1-03 | B07 | lane #1 | nặng | Camera bên yêu cầu `position = other`. |
| 27 | QC1-03 | B07 | lane #2 | nặng | Camera bên yêu cầu `position = other`. |
| 28 | QC1-03 | B07 | lane #5 | nặng | Camera bên yêu cầu `position = other`. |
| 29 | QC1-03 | A09 | lane #3 | nặng | Vạch trắng đứt bên phải làn đang mang L1. Đổi thành R1. |
| 30 | QC1-06 | A09 | lane #3 | chính | Vạch trắng đứt đang mang `style = solid`. Đổi thành `dashed`. |
| 31 | QC1-06 | A09 | lane #1 và #4 | chính | Hai sọc cùng một vạch trắng đôi được gán thành hai vạch đơn. Gán một polyline theo tâm cụm với `kind = double` và `position = L1`. |
| 32 | QC1-08 | A06 | traffic_light #10 | nặng | Đèn hướng về xe đang sáng xanh, XML ghi `red`. |
| 33 | QC1-08 | A06 | traffic_light #14 | nặng | Đèn hướng về xe đang sáng xanh, XML ghi `red`. |
| 34 | QC1-08 | A06 | traffic_light #15 | nặng | Đèn hướng về xe đang sáng xanh, XML ghi `red`. |
| 35 | QC1-08 | A08 | traffic_light #1 | nặng | Đèn hướng về xe đang sáng xanh, XML ghi `red`. |
| 36 | QC1-08 | A08 | traffic_light #17 | nặng | Đèn hướng về xe đang sáng xanh, XML ghi `red`. |
| 37 | QC1-08 | A08 | traffic_light #18 | nặng | Đèn hướng về xe đang sáng xanh, XML ghi `red`. |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp |
| --- | --- | --- |
| A05 | Ảnh không thấy vạch sơn phân làn. Xác nhận để trống L1 và R1? | Chờ xác nhận |
| A06 | Không thấy rõ vạch sơn bên phải làn xe. Xác nhận để trống R1? | Chờ xác nhận |
| A08 | Hai đường lane #10 và #25 nằm phía trái giao lộ. Xác định #10 có phải L1 và #25 có phải vạch dừng để bỏ khỏi lane không? | Chờ xác nhận |
| B06, B07 | Lint gợi ý rà độ bám cung ở road_curb #1 (B06) và lane #2, #5 (B07). Cần kiểm ở ảnh gốc phóng to để kết luận mức lệch. | Chờ xác nhận |

## Quyết định

**Rework.** Mẫu có **17 lỗi nặng**, **2 lỗi chính / 65 nhãn = 3,08%** và **18 lỗi nhẹ**. Còn bốn dòng ca cần xác nhận. Chỉ riêng lỗi thiếu tag camera cũng đủ để yêu cầu Rework.

Rà tự động ngoài mẫu cho thấy cả 20 ảnh trong hai ZIP đều thiếu camera, timeofday, weather và source. Số liệu ngoài mẫu không được cộng vào bảng trên.

