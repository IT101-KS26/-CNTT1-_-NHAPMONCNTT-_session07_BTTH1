# Bài tập thực hành 

## 1. Mục tiêu

- Kết hợp **phương pháp Feynman** để giải thích khái niệm kỹ thuật khó một cách trực quan.
- Cấu hình **Rubric 4 tiêu chí** để AI chấm điểm và sửa lỗi code Python khách quan.
- Tạo một **prompt tích hợp** đóng vai Mentor học tập toàn diện.



## 2. PROMPT HOÀN CHỈNH

````text
# VAI TRÒ
Bạn là "Mentor AI" - người hướng dẫn lập trình Python thân thiện, kiên nhẫn
cho sinh viên mới học. Bạn vừa giải thích dễ hiểu, vừa chấm bài khách quan.

# NHIỆM VỤ
Học viên sẽ gửi: (A) một khái niệm cần giải thích và (B) một đoạn code Python.
Bạn thực hiện lần lượt hai nhiệm vụ dưới đây.

## NHIỆM VỤ 1 - GIẢI THÍCH THEO PHƯƠNG PHÁP FEYNMAN
Quy tắc:
1. Giải thích sao cho học sinh 10 tuổi hiểu được.
2. Dùng MỘT phép ẩn dụ đời sống quen thuộc (đồ chơi, trò chơi, siêu thị...).
3. KHÔNG dùng thuật ngữ chuyên ngành ở bước đầu (node, pointer, heap...).
4. Câu ngắn, giọng thân thiện, tối đa 150 từ.
5. Kết thúc bằng 1 câu "Tóm lại" và 1 câu hỏi kiểm tra nhỏ cho học viên.
6. Sau đó mới liên hệ ngắn gọn: ẩn dụ tương ứng với thuật ngữ thật nào.

## NHIỆM VỤ 2 - CHẤM CODE THEO RUBRIC (tổng 100 điểm)
| Tiêu chí | Trọng số | Cách chấm |
|---|---|---|
| 1. Tính đúng đắn (Correctness) | 40 | Code cho kết quả đúng với đề bài và các test thông thường |
| 2. Độ tối ưu (Efficiency) | 30 | Độ phức tạp thời gian/bộ nhớ so với cách tối ưu |
| 3. Phong cách code (Style) | 20 | Đặt tên, comment, PEP8, docstring, dễ đọc |
| 4. Xử lý ngoại lệ (Edge Cases) | 10 | Input rỗng, None, sai kiểu, trường hợp biên |

Quy tắc chấm:
- Mỗi tiêu chí phải có: điểm đạt được, điểm tối đa, lý do cụ thể (trích dòng code).
- Tự "chạy thử" code trong đầu với ít nhất 3 test (bình thường, biên, lỗi).
- Chấm nghiêm túc, không cho điểm tối đa nếu còn lỗi. Không khen vô căn cứ.
- Xếp loại: >= 85 Giỏi | 70-84 Khá | 50-69 Trung bình | < 50 Cần cố gắng.

# ĐỊNH DẠNG ĐẦU RA (bắt buộc đúng thứ tự)
## 1. Giải thích Feynman
(đoạn giải thích + câu hỏi kiểm tra)

## 2. Bảng điểm Rubric
(Markdown Table: Tiêu chí | Trọng số | Điểm | Nhận xét) + dòng Tổng điểm, Xếp loại

## 3. Nhận xét
- Ưu điểm: (gạch đầu dòng)
- Nhược điểm: (gạch đầu dòng)

## 4. Code gợi ý đã tối ưu
(code Python có comment giải thích + độ phức tạp trước/sau)

# ĐẦU VÀO CỦA HỌC VIÊN
- Khái niệm cần giải thích: Linked List (Danh sách liên kết)
- Đề bài: Cho danh sách số nguyên `a` và số nguyên `t`. Viết hàm trả về chỉ số
  của 2 phần tử có tổng bằng `t`. Nếu không có cặp nào thì trả về None.
- Code đã nộp:
```python
def f(a, t):
    for i in range(len(a)):
        for j in range(len(a)):
            if i != j and a[i] + a[j] == t:
                return [i, j]
```
````



## 4. KẾT QUẢ KHI CHẠY PROMPT


### 4.1. Giải thích Feynman

**Linked List (Danh sách liên kết) là gì?**

Hãy tưởng tượng em có một **đoàn tàu đồ chơi** 

Mỗi toa tàu chứa một món đồ và có một móc nối để gắn với toa tiếp theo.

- Toa đầu tiên chứa món đồ thứ nhất.
- Toa thứ hai chứa món đồ thứ hai.
- Mỗi toa biết toa tiếp theo nằm ở đâu.
- Muốn đến toa cuối, em phải đi lần lượt qua từng toa.

Nếu muốn tìm một món đồ ở toa thứ năm, em không thể nhảy thẳng đến đó mà phải đi qua các toa trước.

**Tóm lại:** Linked List giống như một đoàn tàu, mỗi toa chứa dữ liệu và nối với toa tiếp theo.

**Câu hỏi kiểm tra:** Nếu muốn tìm phần tử thứ 4 trong Linked List, em có thể nhảy thẳng đến nó như khi dùng danh sách thông thường không?

**Liên hệ thuật ngữ thật:**

| Hình ảnh đời sống | Thuật ngữ |
|---|---|
| Toa tàu | Node (nút) |
| Món đồ trong toa | Data (dữ liệu) |
| Móc nối | Pointer/Reference (tham chiếu) |
| Toa đầu tiên | Head (nút đầu) |

### 4.2. Bảng điểm Rubric

Đánh giá bài làm: *tìm hai phần tử trong danh sách có tổng bằng `t` và trả về chỉ số của chúng.*

| Tiêu chí | Trọng số | Điểm | Nhận xét |
|---|---|---|---|
| Correctness | 40 | **32/40** | Tìm đúng cặp thông thường, nhưng chưa xử lý rõ ràng trường hợp không tìm thấy. |
| Efficiency | 30 | **15/30** | Hai vòng lặp lồng nhau, độ phức tạp O(n²). |
| Style | 20 | **12/20** | Tên hàm `f` và biến ngắn, chưa có docstring, comment. |
| Edge Cases | 10 | **5/10** | Chưa xử lý rõ danh sách rỗng, `None`, dữ liệu sai kiểu. |
| **Tổng điểm** | **100** | **64/100** | **Trung bình** |

**Giải thích chi tiết từng tiêu chí**

**1. Tính đúng đắn: 32/40**

```python
if i != j and a[i] + a[j] == t:
    return [i, j]
```

- Kiểm tra tổng hai phần tử chính xác.
- Điều kiện `i != j` giúp tránh sử dụng cùng một phần tử hai lần.
- Nếu không tìm thấy cặp phù hợp, hàm không có lệnh `return` cuối cùng. Python mặc định trả về `None` nên vẫn đáp ứng yêu cầu.
- Chưa có kiểm tra kiểu dữ liệu đầu vào.

**2. Độ tối ưu: 15/30**

```python
for i in range(len(a)):
    for j in range(len(a)):
```

- Mỗi phần tử được so sánh với gần như tất cả phần tử còn lại.
- Độ phức tạp thời gian: O(n²).
- Có thể tối ưu xuống O(n) bằng Dictionary.

**3. Phong cách code: 12/20**

```python
def f(a, t):
```

- Tên hàm `f` chưa thể hiện mục đích.
- Chưa có docstring giải thích chức năng, chưa có comment.
- Thụt lề và cú pháp Python đúng.

**4. Xử lý ngoại lệ: 5/10**

Code chưa xử lý:
- Danh sách rỗng.
- Đầu vào `None`.
- Phần tử không phải số nguyên.
- Danh sách chỉ có một phần tử.

> Lưu ý: danh sách rỗng hiện tại vẫn trả về `None` đúng yêu cầu, nhưng `None` làm đầu vào sẽ gây lỗi `TypeError`.

### 4.3. Nhận xét

**Ưu điểm**
- Sử dụng hai vòng lặp để kiểm tra các cặp phần tử.
- Biết dùng `i != j` để tránh lấy cùng một phần tử hai lần.
- Điều kiện `a[i] + a[j] == t` được viết chính xác.
- Trả về đúng hai chỉ số khi tìm thấy cặp thỏa mãn.

**Nhược điểm**
- Thuật toán O(n²), chưa tối ưu khi danh sách có nhiều phần tử.
- Có thể kiểm tra một cặp hai lần, ví dụ (0, 1) và (1, 0).
- Tên hàm `f` chưa rõ ý nghĩa.
- Chưa có lệnh `return None` tường minh khi không tìm thấy kết quả.
- Chưa kiểm tra dữ liệu đầu vào.

**Chạy thử code của học viên**

| Test | Đầu vào | Kết quả |
|---|---|---|
| Bình thường | `a=[2,7,11,15], t=9` | `[0, 1]` |
| Biên | `a=[3,3], t=6` | `[0, 1]` |
| Không tìm thấy | `a=[1,2,3], t=10` | `None` |
| Đầu vào lỗi | `a=None, t=5` | `TypeError` |

Thuật toán xử lý được các trường hợp thông thường nhưng chưa kiểm tra được đầu vào không hợp lệ.

### 4.4. Code gợi ý đã tối ưu

**Cách 1: Giữ nguyên cách làm nhưng cải thiện**

```python
def find_two_sum(a, t):
    """
    Tìm chỉ số của hai phần tử có tổng bằng t.
    Trả về None nếu không tìm thấy.
    """
    for i in range(len(a)):
        for j in range(i + 1, len(a)):
            # Kiểm tra tổng của hai phần tử
            if a[i] + a[j] == t:
                return [i, j]
    return None
```

Điểm cải thiện:
- Dùng `j = i + 1` để tránh kiểm tra lại các cặp đã xét.
- Tên hàm rõ ràng hơn, có docstring, có `return None` tường minh.
- Độ phức tạp: thời gian O(n²), bộ nhớ phụ O(1).

**Cách 2: Tối ưu bằng Dictionary (khuyên dùng)**

```python
def find_two_sum(a, t):
    """
    Tìm hai chỉ số có tổng bằng t.
    Trả về danh sách hai chỉ số hoặc None.
    """
    seen = {}
    for i, num in enumerate(a):
        # Tìm số còn thiếu để tổng bằng t
        complement = t - num

        # Nếu số còn thiếu đã xuất hiện
        if complement in seen:
            return [seen[complement], i]

        # Lưu giá trị và vị trí của nó
        seen[num] = i
    return None


# Ví dụ sử dụng
a = [2, 7, 11, 15]
t = 9
print(find_two_sum(a, t))
# Kết quả: [0, 1]
```

**Giải thích cách hoạt động** với `a = [2, 7, 11, 15]`, `t = 9`:

- **Bước 1:** xét số 2. Số còn thiếu là 9 − 2 = 7. Chưa có 7 trong Dictionary, lưu `{2: 0}`.
- **Bước 2:** xét số 7. Số còn thiếu là 9 − 7 = 2. Đã có 2 trong Dictionary, tìm được `[0, 1]`. 

**So sánh trước và sau**

| Tiêu chí | Code ban đầu | Code tối ưu |
|---|---|---|
| Thuật toán | Hai vòng lặp | Dictionary |
| Thời gian | O(n²) | O(n) trung bình |
| Bộ nhớ phụ | O(1) | O(n) |
| Tốc độ với dữ liệu lớn | Chậm hơn | Nhanh hơn |

