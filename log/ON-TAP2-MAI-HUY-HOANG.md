


# BÀI LÀM – ÔN TẬP NGÀY 2



-   **Họ tên:**  MAI HUY HOÀNG 
-   **Lớp:**  HN-KS26-CNTT1
-   **Link repository:**    (https://github.com/maihuyhoang19012008-jpg/cntt1_nhap-mon-CNTT_OnTap-Ngay2/upload) 
-   **Hệ điều hành (Windows/macOS):**   WIN 

## Bài 1. Lọc log thủ công


### Lệnh đã chạy


grep "ERROR" logs/access.log > logs/error_report.txt
cat logs/error_report.txt

### 2 dòng lỗi đầu tiên trong error_report.txt


```
2025-10-18 09:15:09 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 09:25:05 [ERROR] Het thoi gian cho (timeout)

```

## Bài 2. Đếm sử dụng pipeline

### Lệnh như sau: 


grep "WARNING" logs/access.log | wc -l
grep "ERROR" logs/payment.log | wc -l

### Kết quả đếm (Windows: giá trị Count )


```
WARNING trong access.log: 4
ERROR trong payment.log: 3

```

## Bài 3. Chạy script auto_warning 


### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

bash auto_warning.sh

### Nội dung file logs/warning_report.txt


```
=== CANH BAO THANH TOAN ===
2025-10-18 09:19:13 [WARNING] Cong thanh toan PHAN HOI
2025-10-18 09:30:16 [WARNING] nhap sai ma OTP qua 5 lan 
2025-10-18 09:40:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 4. Báo cáo tổng hợp


### Các lệnh đã chạy



```echo "=== TONG HOP ACCESS LOG ===" > logs/tong_hop_ngay2.txt
grep "ERROR" logs/access.log >> logs/tong_hop_ngay2.txt
grep "WARNING" logs/payment.log | wc -l >> logs/tong_hop_ngay2.txt```

### Nội dung file logs/tong_hop_ngay2.txt


```
=== TONG HOP ACCESS LOG ===
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)
5



## Bài 5. Câu hỏi ngắn

-   **a)**  Dấu  `>`  dùng để ghi mới, nếu trong file đã có chữ thì xoá sạch rồi mới ghi nội dung mới vào. Dấu  `>>`  giữ lại nội dung cũ và viết nối tiếp phần mới vào cuối file
-   **b)**  File sẽ mất dòng tiêu đề  `=== TONG HOP ACCESS LOG ===`  mà lệnh 1 vừa ghi, vì lệnh thứ 2 đã dùng dấu  `>`nên nó đã xoá sạch nội dung cũ. File còn lại chỉ có 6 dòng ERROR mà không có tiêu đề.
-   **c)**  Vì đường dẫn tuyệt đối gắn chặt với từng máy, /Users/dangminhhuyen/... chỉ đúng với máy mình, nếu sang máy khác là máy đó không tìm thấy file và báo lỗi. Dùng đường dẫn tương đối logs/payment.log chỉ cần giữ nguyên thư mục là sang máy nào cũng chạy được,  cho người khác cũng không cần phải sửa lại đường dẫn

## Tự chấm (điền khi có đáp án)

-   **Điểm tự chấm:**  ....... ..../100
-   LỖI VÀ SỬA LỖI :  
