# Mô hình MVC:
- Mô hình MVC được chia làm 3 lớp xử lý gồm Model – View – Controller:
	1. Model: xử lý truy vấn database như thêm/xóa/sửa
	2. View: là nới chứa những giao diện như một nút bấm, khung nhập, menu, hình ảnh… nó đảm nhiệm nhiệm vụ hiển thị dữ liệu và giúp người dùng tương tác với hệ thống
	3. Controller: bắt những sự kiện mà người dùng yêu cầu, thực hiện các tác vụ xử lý logic lấy đúng dữ liệu cần thiết nhờ các nghiệp vụ mà lớp Model cung cấp và trả về dữ liệu cho View hiển thị
- Sự tương tác giữa các thành phần:
	1. Controller tương tác qua lại với View
	2. Controller tương tác qua lại với Model
	3. Model và view tương tác với nhau thông qua Controller

![enter image description here](https://images.viblo.asia/243b3d41-ec57-4d3f-8d8b-c2d4db8a467f.png)

- Ưu điểm:
1. Đây là một mô hình với kết cấu tương đối đơn giản, dễ hiểu
2. MVC cho phép dễ dàng kiểm tra, rà soát lỗi phần mềm trước khi tới tay người tiêu dùng, đảm bảo chất lượng và độ uy tín cao
- Nhược điểm:
3. Mô hình MVC thường được sử dụng vào những dự án lớn. Do đó, với các dự án nhỏ, mô hình MVC có thể gây cồng kềnh, tốn thời gian trong quá trình phát triển cũng như thời gian trung chuyển dữ liệu
