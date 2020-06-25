# array:
1. Khai báo mảng
2. Dùng hàm Length để lấy số lượng phần tử của mảng
3. Gọi hàm push(), append() để thêm phần tử và delete() để xóa phần tử
4. insert(4, "abcd") dùng để thêm vào vị trí thứ 4 phần tử "abcd"
5. delete_at(2) dùng để xóa phần tử tại vị trí số 2
6. delete(1) dùng đế xóa tất cả các phần tử có giá trị là 1
7. uniq() dùng để loại bỏ các phần tử trùng lặp
8. Dùng map hoặc each để duyệt mảng
9. select {|val| val > 4} dùng để chọn phần tử có gía trị lớn hơn 4
10. reject { |val| val < 4 } dùng để loại bỏ phần tử có giá trị nhỏ hơn 4
## hash:
1. Khởi tạo hash: hash = {}
2. Mỗi phần tử của hash là cặp key và value. Vd: hash[key] = value
3. Hàm has_key?() để kiểm tra xem key đã tồn tại hay chưa
4. Hàm has_value?() để kiểm tra value đã tồn tại hay chưa
5. Hàm delete(key) dùng để xóa phần tử có khóa là key
6. Hàm delete_if {|key, value| value > 4 } dùng để xóa phần tử với điều kiện value > 4
7. Hàm each để duyệt tất cả các phần tử của hash
8. Hàm select {|key, value| value >  4} chọn ra các phần tử có value lớn hơn 4
9. Hàm to_a để chuyển hash sang array với mỗi phần tử là 1 mảng con có giá trị là [key, value]

## File IO
1. dir.glob("*") dùng để liệt kê tất cả các file trong thư mục hiện tại và tất cả các thư mục con
2. dir.glob(đuôi_file) dùng để liệt kê các file 
3. dir.pwd dùng để lấy đường dẫn thư mục hiện tại
4. dir.home dùng để lấy đường dẫn home của máy tính
5. dir.mkdir("tên_folder") dùng để tạo thư mục có tên là "tên_folder"
6. dir.rmdir("tên_folder") dùng để xóa thư mục có tên là "tên_folder"
7. dir.exists? dùng để kiểm tra thư mục có tồn tại hay không
8. file.absolute_path dùng để lấy đường dẫn tuyệt đối của file
9. File.basename(path) dùng để lấy tên của file kèm theo đuôi file
10. File.extname(path) dùng để lấy đuôi file 
11. File.dirname(path) dùng để lấy đường dẫn chưa file đó
12. Ghi file:
File.open("hello.txt", "w") do |file|	# nếu file hello.txt không tồn tại thì tự động được tạo
  file.puts "nội dung file"
end
13. Đọc file
File.open("hello.txt", "r") do |file|
  while line = file.gets
	  line	# nội dung 1 dòng đọc được từ file
  end
end
