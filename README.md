# BÀI TẬP: THIẾT KẾ ĐÓNG GÓI LỚP HỌC VIÊN (STUDENT)

- **Môn học:** IT105 - Phân tích & Thiết kế Phần mềm
- **Bài tập:** Session 07 - Bài 1
- **Sinh viên:** Nguyễn Tuấn Khang

---

## 1. Phần 1: Sơ đồ Class Diagram

Sơ đồ lớp `Student` hoàn chỉnh được vẽ theo chuẩn UML với đầy đủ bổ từ truy cập:

![Sơ đồ Class Diagram](class_diagram.png)

- File thiết kế gốc (Draw.io): [class_diagram.drawio](class_diagram.drawio)

### Bảng ký hiệu bổ từ truy cập:
| Ký hiệu UML | Bổ từ truy cập | Phạm vi truy cập | Áp dụng trong lớp Student |
| :---: | :--- | :--- | :--- |
| **`-`** | Private | Chỉ nội bộ trong lớp | Áp dụng cho các thuộc tính: `studentId`, `name`, `score` |
| **`+`** | Public | Truy cập công khai từ bên ngoài | Áp dụng cho constructor, các hàm getter/setter và `displayInfo()` |
| **`#`** | Protected | Trong lớp và các lớp con kế thừa | Dự phòng mở rộng |
| **`~`** | Package | Trong cùng package | Mặc định |

---

## 2. Phần 2: Mô tả Logic an toàn cho phương thức `setScore()`

### 2.1. Mã giả (Pseudocode)
```text
METHOD setScore(newScore: Real) -> Boolean:
    IF newScore >= 0.0 AND newScore <= 10.0 THEN
        this.score = newScore
        RETURN True
    ELSE
        PRINT "Lỗi: Điểm số phải nằm trong khoảng từ 0 đến 10!"
        RETURN False
    END IF
END METHOD
```

### 2.2. Giải thích logic
- **Điều kiện kiểm tra:** `newScore >= 0.0 AND newScore <= 10.0` chặn các giá trị điểm âm hoặc vượt quá 10.
- **Nếu hợp lệ:** Cập nhật `this.score = newScore`.
- **Nếu vi phạm:** Không gán giá trị mới (giữ nguyên điểm cũ) và in thông báo lỗi.

### 2.3. Bảng kiểm tra ca dữ liệu (Test cases):
| Trường hợp | Giá trị `newScore` | Xử lý | Trạng thái `score` |
| :--- | :---: | :--- | :--- |
| Điểm hợp lệ | `8.5` | Chấp nhận | `score = 8.5` |
| Biên dưới | `0.0` | Chấp nhận | `score = 0.0` |
| Biên trên | `10.0` | Chấp nhận | `score = 10.0` |
| Điểm âm | `-1.0` | Từ chối, báo lỗi | Giữ điểm cũ |
| Điểm lớn hơn 10 | `11.5` | Từ chối, báo lỗi | Giữ điểm cũ |

---

## 3. Tài liệu nộp kèm
- File báo cáo Word: [BaoCao_ThietKe_DongGoi_Lop_HocVien.docx](BaoCao_ThietKe_DongGoi_Lop_HocVien.docx)
- File vẽ: [class_diagram.drawio](class_diagram.drawio)
- Ảnh sơ đồ: [class_diagram.png](class_diagram.png)
