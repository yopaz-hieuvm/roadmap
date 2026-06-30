## SQL Basic

* SQL là ngôn ngữ dùng để làm việc với cơ sở dữ liệu quan hệ
* Dùng để tạo bảng, thêm, sửa, xóa và truy vấn dữ liệu

**Các câu lệnh cơ bản**

```sql
SELECT
INSERT
UPDATE
DELETE
CREATE
ALTER
DROP
```
## JOIN

Dùng để kết hợp dữ liệu từ nhiều bảng

**Các loại JOIN**

* **INNER JOIN**: Lấy dữ liệu khớp ở cả hai bảng
* **LEFT JOIN**: Lấy toàn bộ dữ liệu bảng trái
* **RIGHT JOIN**: Lấy toàn bộ dữ liệu bảng phải
* **FULL JOIN**: Lấy toàn bộ dữ liệu của hai bảng
* **CROSS JOIN**: Kết hợp mọi dòng của hai bảng
* **SELF JOIN**: Join với chính bảng đó

## Aggregate

Dùng để thống kê dữ liệu và trả về 1 giá trị

**Các hàm phổ biến**

* `COUNT()`

* `SUM()`

* `AVG()`

* `MAX()`

* `MIN()`

* `GROUP BY`: Nhóm dữ liệu

* `HAVING`: Lọc dữ liệu sau khi `GROUP BY`


## Database Design

Thiết kế cấu trúc database để

* Tránh dữ liệu trùng lặp
* Dễ mở rộng
* Dễ bảo trì
* Đảm bảo tính toàn vẹn dữ liệu
* Tăng hiệu năng truy vấn

### Quy trình thiết kế Database
1. Phân tích yêu cầu
* Hiểu bải toán cần giải quyết
* Xác đinh nghiệp vụ hệ thống
* Xác định dữ liệu cần lưu trữ
2. Xác định thực thể
* Xác định các đối tượng chính của hệ thống
* Mỗi Entity thường tương ứng với 1 bảng trong database
3. Xác định atrribute
* xác định trường dữ liệu của mỗi entity
* lựa chọn kiểu dữ liệu phù hợp
* xác định cột bắt buộc và cột tùy chọn
4. Xác định Relationship
* Thiết lập mỗi quan hệ giữa các bảng ( 1-1, 1-N, N-N)
5. Chuẩn hóa dữ liệu (Normalization) <br>
Mục tiêu:
- Loại bỏ dữ liệu dư thừa
- Tránh bất nhất dữ liệu
- Giảm lỗi khi cập nhật
- Dễ bảo trì và mở rộng<br>
Các mức chuẩn thường gặp:  1NF - 2NF - 3NF
6. Thiết lập Constraint<br>
Đảm bảo dữ liệu luôn hợp lệ
- Primary Key
- Foreign Key 
- Unique 
- Not Null 
- Check 
- Default
7. Thiết kế Index<br>
Tạo Index cho các cột thường được sử dụng trong:
- WHERE
- JOIN
- ORDER BY
- GROUP BY
8. Kiểm tra và tối ưu
  - Kiểm tra các câu truy vấn
  - Phân tích Execution Plan
  - Tối ưu Index
  - Điều chỉnh cấu trúc bảng nếu cần
  - Đảm bảo Database đáp ứng yêu cầu về hiệu năng

## Migrations

Quản lý thay đổi cấu trúc database bằng code

**Lợi ích**

* Tạo và sửa bảng
* Quản lý phiên bản Database
* Đồng bộ database giữa các môi trường
* Có thể rollback khi cần
* Review qua git


## Constraint

là các ràng buộc đảm bảo dữ liệu luôn hợp lệ và nhất quán

* **PRIMARY KEY**: Khóa chính.
* **FOREIGN KEY**: Khóa ngoại.
* **UNIQUE**: Không cho phép trùng.
* **NOT NULL**: Không được để trống.
* **CHECK**: Kiểm tra điều kiện.
* **DEFAULT**: Giá trị mặc định.


## Index

Index giúp tăng tốc truy vấn bằng cách giảm số lượng bản ghi cần đọc, giống như mục lục của một cuốn sách

### Tại sao Index nhanh hơn?

* Không có Index → Quét toàn bộ bảng (**Full Table Scan**).
* Có Index → Tìm kiếm bằng **B-Tree**, giảm số lượng bản ghi cần đọc.

### Các loại Index

**MySQL**

* Primary Index
* Unique Index
* Normal Index
* Composite Index
* Fulltext Index
* Spatial Index

**PostgreSQL**

* B-Tree
* Hash
* GIN
* GiST
* BRIN
* SP-GiST

### Khi nào nên dùng?

* Cột thường xuất hiện trong `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`.
* Khóa chính và khóa ngoại.
* Cột có nhiều giá trị khác nhau (high cardinality).

### Khi nào không nên dùng?

* Bảng nhỏ.
* Cột ít được truy vấn.
* Cột chỉ có vài giá trị (ví dụ: `status`, `gender`).

### Đánh nhiều Index có ảnh hưởng gì?

* Tốn dung lượng lưu trữ.
* `INSERT`, `UPDATE`, `DELETE` chậm hơn.
* Tăng chi phí bảo trì Index.

## N+1 Problem

Xảy ra khi thực hiện:

* 1 query lấy danh sách.
* N query lấy dữ liệu liên quan.

**Tác hại**

* Tăng số lượng query.
* Giảm hiệu năng.

**Cách khắc phục**

* Sử dụng `JOIN`.
* Sử dụng Eager Loading (`with()` trong Laravel).

