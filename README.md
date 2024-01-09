# sql-learning

## 1. SQL là gì?

**SQL** là viết tắt của **Structured Query Language** hay ngôn ngữ truy vấn cấu trúc. Nó được thiết kế để tương tác với dữ liệu trong hệ quản trị cơ sở dữ liệu quan hệ (**RDBMS - Relational Database Management System**)

## 2. Định nghĩa JOIN và các loại JOIN

SQL JOIN được dùng để kết hợp dữ liệu từ 2 hay nhiều bảng dựa trên các cột có liên quan giữa các bảng đó.

![SQL joins!](https://i.stack.imgur.com/4zjxm.png "SQL Joins")

### 2.1. Các loại JOIN

Có 4 loại JOIN trong SQL:
- **INNER JOIN**: truy suất các records có giá trị trùng khớp với phép JOIN ở cả 2 bảng.
- **LEFT (OUTER) JOIN**: truy suất tất cả records của bảng bên trái cùng các records phù hợp ở bảng bên phải.
- **RIGHT (OUTER) JOIN**: truy suất tất cả records của bảng bên phải cùng các records phù hợp ở bảng bên trái.
- **FULL (OUTER) JOIN**: truy suất tất cả các records khớp với phép JOIN hoặc ở bảng bên trái hoặc ở bảng bên phải.

### 2.2. Self-join

Là lệnh JOIN là trường hợp một bảng tự join với chính bảng đó thông qua các columns của nó.

### 2.3 Cross-join

- Lệnh cross-join được định nghĩa là tích Đề-các (Descartes) của 2 bảng trong phép join. Có nghĩa là sau khi join thì kết quá nhận được m x n records với m là số records của Table_A và n là số records của Table_B.
- Lệnh **CROSS JOIN** không cần bổ sung điều kiện join để thực hiện. Tuy nhiên nếu sử dụng mệnh đề **WHERE** trong một câu lệnh cross join thì nó sẽ làm việc giống như một lênh **INNER JOIN**.

## 3. DELETE, TRUNCATE và DROP

- **DELETE**: dùng để một hoặc nhiều records từ 1 table cụ thể thông qua điều kiện WHERE. Khi thực hiện **DELETE** nó sẽ không xóa ngay dữ liệu mà sẽ chuyển dữ liệu đó vào **transaction log**, do đó có thể ROLLBACK dữ liệu đã xóa nếu cần thiết.
- **TRUNCATE**: dùng để xóa toàn bộ records của một table và không thể ROLLBACK dữ liệu đã xóa.
- **DROP**: dùng để xóa một table khỏi database bao gồm tất cả records của table, indexes, constraint, triggers, ...

## 4. MINUS, UNION, UNION ALL, INTERSECT

Các lệnh này được dùng để kết hợp dữ liệu từ nhiều câu truy vấn

- **MINUS**: trả về các records chỉ có trong câu truy vấn 1.
- **UNION**: trả về tất cả records kết hợp từ 2 câu truy vấn và loại những records trùng nhau.
- **UNION ALL**: trả về tất cả records kết hợp từ 2 câu truy vấn kể cả những records trùng nhau.
- **INTERSECT**: trả về những records trùng nhau từ 2 câu truy vấn.

## 5. PRIMARY KEY, UNIQUE CONSTRAINT vs. FOREIGN KEY

- Ràng buộc **PRIMARY KEY** dùng để xác định duy nhất mỗi hàng trong một bảng. Nó phải chứa các giá trị **UNIQUE** và **NOT NULL**. Mỗi table chỉ chứa duy nhất một **PRIMARY KEY**
- Ràng buộc **UNIQUE** đảm bảo rằng tất cả các giá trị trong một cột phải khác nhau. Nó chứa các giá trị **UNIQUE** nhưng cho phép các giá trị **NULL**. Không giống **PRIMARY KEY**, mỗi table có thể chứa nhiều ràng buộc **UNIQUE**
- **clustered index** được tạo tự động khi **PRIMARY KEY** được defined trong khi **UNIQUE CONSTRAINT** tạo **non-clustered index**
- Một **FOREIGN KEY** bao gồm một hoặc tập hợp các fields trong bảng mà tham chiếu đến **PRIMARY KEY** của các bảng khác. Nó đảm bảo tính toàn vẹn tham chiếu trong mối quan hệ giữa 2 table.

## 6. Index

Index được dùng để tăng tốc độ truy vấn dữ liệu.
