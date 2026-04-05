# Report 1 Page – FIT4012 Lab 1

## 1. Mục tiêu
Tóm tắt ngắn gọn mục tiêu của bài lab.

## 2. Cách làm
- Đọc hiểu chương trình entropy mẫu.
- Bổ sung hàm tính redundancy.
- Hoàn thiện hàm mod_inverse().
- Chạy thử trên nhiều test case.

## 3. Kết quả chính
### 3.1 Entropy và redundancy
| Input | Entropy | Redundancy | Nhận xét |
|---|---:|---:|---|
| aaaa | 0.0000 | 8.0000 | Chuỗi chỉ có 1 ký tự lặp lại nên entropy bằng 0, dữ liệu rất dễ đoán và độ dư thừa rất cao. |
| abcd | 2.0000 | 6.0000 | 4 ký tự xuất hiện đều nhau nên entropy cao hơn trường hợp `aaaa`, nhưng vẫn thấp hơn entropy tối đa của bảng mã ASCII. |
| hello world | 2.8454 | 5.1546 | Chuỗi có độ đa dạng ký tự lớn hơn, nhưng vẫn có lặp lại như `l`, `o` và dấu cách nên entropy chưa cao. |

### 3.2 Modulo inverse
| a | m | Kết quả mong đợi | Kết quả chương trình |
|---:|---:|---|---|
| 3 | 7 | 5 | 5 |
| 10 | 17 | 12 | 12 |
| 6 | 9 | Không tồn tại | Không tồn tại |

## 4. Kết luận
Qua bài lab này, em hiểu rõ hơn rằng entropy dùng để đo mức độ ngẫu nhiên của dữ liệu: chuỗi càng lặp lại nhiều thì entropy càng thấp và redundancy càng cao. Em cũng hiểu rõ hơn điều kiện để một số có nghịch đảo modulo là `gcd(a, m) = 1`, và cách thuật toán Euclid mở rộng giúp tìm ra hệ số thỏa mãn phương trình. Khó khăn lớn nhất của em là phân biệt giữa ý nghĩa toán học của công thức và cách cài đặt chúng trong chương trình C++. Điều giúp em hiểu rõ hơn là tự chạy nhiều test case khác nhau và so sánh kết quả giữa trường hợp có quy luật rõ ràng như `aaaa` với trường hợp đa dạng hơn như `hello world`.