## SQL Basic

* SQL là ngôn ngữ dùng để làm việc với cơ sở dữ liệu quan hệ.
* Dùng để tạo bảng, thêm, sửa, xóa và truy vấn dữ liệu.

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

Dùng để kết hợp dữ liệu từ nhiều bảng.

**Các loại JOIN**

* **INNER JOIN**: Lấy dữ liệu khớp ở cả hai bảng.
* **LEFT JOIN**: Lấy toàn bộ dữ liệu bảng trái.
* **RIGHT JOIN**: Lấy toàn bộ dữ liệu bảng phải.
* **FULL JOIN**: Lấy toàn bộ dữ liệu của hai bảng.
* **CROSS JOIN**: Kết hợp mọi dòng của hai bảng.
* **SELF JOIN**: Join với chính bảng đó.

## Aggregate

Dùng để thống kê dữ liệu.

**Các hàm phổ biến**

* `COUNT()`

* `SUM()`

* `AVG()`

* `MAX()`

* `MIN()`

* `GROUP BY`: Nhóm dữ liệu.

* `HAVING`: Lọc dữ liệu sau khi `GROUP BY`.


## Database Design

Thiết kế cấu trúc database để:

* Tránh dữ liệu trùng lặp.
* Dễ mở rộng.
* Dễ bảo trì.
* Đảm bảo tính toàn vẹn dữ liệu.


## Migrations

Quản lý thay đổi cấu trúc database bằng code.

**Lợi ích**

* Tạo và sửa bảng.
* Đồng bộ database giữa các môi trường.
* Có thể rollback khi cần.


## Constraint

Đảm bảo dữ liệu luôn hợp lệ.

* **PRIMARY KEY**: Khóa chính.
* **FOREIGN KEY**: Khóa ngoại.
* **UNIQUE**: Không cho phép trùng.
* **NOT NULL**: Không được để trống.
* **CHECK**: Kiểm tra điều kiện.
* **DEFAULT**: Giá trị mặc định.


## Index

Index giúp tăng tốc truy vấn, giống như mục lục của một cuốn sách.

### Tăng tốc

* `WHERE`
* `JOIN`
* `ORDER BY`
* `GROUP BY`

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

