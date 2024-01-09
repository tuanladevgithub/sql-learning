# sql-learning

## 1. SQL là gì?

**SQL** là viết tắt của **Structured Query Language** hay ngôn ngữ truy vấn cấu trúc. Nó được thiết kế để tương tác với dữ liệu trong hệ quản trị cơ sở dữ liệu quan hệ (**RDBMS - Relational Database Management System**)

## 2. Định nghĩa JOIN và các loại JOIN

SQL JOIN được dùng để kết hợp dữ liệu từ 2 hay nhiều bảng dựa trên các cột có liên quan giữa các bảng đó.

![SQL joins!](https://i.stack.imgur.com/4zjxm.png "SQL Joins")

Có 4 kiểu JOIN:
- **INNER JOIN**: truy suất các records có giá trị trùng khớp với phép JOIN ở cả 2 bảng.
- **LEFT (OUTER) JOIN**: truy suất tất cả records của bảng bên trái cùng các records phù hợp ở bảng bên phải.
- **RIGHT (OUTER) JOIN**: truy suất tất cả records của bảng bên phải cùng các records phù hợp ở bảng bên trái.
- **FULL (OUTER) JOIN**: truy suất tất cả các records khớp với phép JOIN hoặc ở bảng bên trái hoặc ở bảng bên phải.

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

## 5. PRIMARY KEY vs. UNIQUE KEY

- Một table chỉ có một **PRIMARY KEY** nhưng có thể có nhiều **UNIQUE KEY**
- **PRIMARY KEY** không chấp nhận NULL, trong khi **UNIQUE KEY** thì chấp nhận cả NULL
- clustered index được tạo tự động khi **PRIMARY KEY** được defined trong khi **UNIQUE KEY** tạo non-clustered index

## 6. Index

Index được dùng để tăng tốc độ truy vấn dữ liệu.
