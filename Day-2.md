# Variable:
Có 5 loại biến
1. Biến cục bộ: phạm vi hoạt động trong class, method
2. $ Biến toàn cục: dùng ở bất cứ đâu trong file
3. Hằng số: bắt đầu bằng chữ hoa. Có thể thay đổi giá trị nhưng sẽ báo warning
4. @ Biến instance: biến chỉ sử dụng trong một đối tượng
5. @@ Biến class: biến class sử dụng cho tất cả các đối tượng của class

## Class Object:
1. getter và setter:
	- attr_reader: tự tạo ra các hàm getter cho các thuộc tính phía sau từ khóa
	- attr_writer: tự tạo ra các hàm setter cho các thuộc tính phía sau từ khóa
	- attr_accessor: tự tạo ra cả các hàm getter và setter cho các thuộc tính phía sau tự khóa
2. Kế thừa:
	- include: đem tất cả các thuộc tính và phương thức của class cha sang cho class con
