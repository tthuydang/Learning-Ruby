# map:
1. Duyệt qua các phần tử của mảng và thực hiện biểu thức trong block, cho phép trả về mảng mới sau khi thực hiện biểu thức trong block
    ví dụ:  a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
            print a.each { |x| x * 3 }
        =>  [3, 6, 9, 12, 15, 18, 21, 24, 27, 30]

    2. Nếu muốn lấy ra những phần tử thỏa điều kiện nào đó thì nó chỉ trả về true hoặc false. Còn select thì có thể
    ví dụ: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10].map{ |i| i < 3 }
        => [true, true, false, false, false, false, false, false, false, false]
##  each:
Duyệt qua các phần tử và thực hiện biểu thức trong block nhưng không cho phép thay đổi mảng ban đầu
    ví dụ:  a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
            print a.each { |x| x * 3 }
        =>  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
## select:
Chọn ra các phần tử thỏa mảng điều kiện trong block, còn biểu thức thì không
    vd 1: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10].select! {|x| x > 3}
    =>    [4, 5, 6, 7, 8, 9, 10]
    vd 2: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10].select! {|x| x * 2}
    =>    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
## collect:
Tương tự mao

## inject:
Tự khởi tạo 1 biến số và cập nhật lại giá trị của nó sau từng phần tử được duyệt
    vd: a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
        print a.inject { |sum, x| sum += x }
    =>  55  # 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10

## detect:

Trả về phần tử đầu tiên thỏa điều kiện trong block
        Nếu biểu thức trong block không phải là 1 biểu thức điều kiện thì sẽ trả về phần tử đầu tiên mà không quan tâm biểu thức đó là gì
    vd1:a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
        print a.detect { |x| x > 3 }
    =>  4
    vd2:a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
        print a.detect { |x| x * 3 }
    => 1


# block:

Về cơ bản thì block giống phương thức mà không có tên và chỉ được sử dụng một lần. Block cũng có tham số như phương thức bình thường
    Tùy số dòng code nhiều hay ít mà ta khai báo block giữa 2 dấu ngoặc nhọn {} hoặc trong khối lệnh do..end
    Khi xử dụng hàm yield thì ta cũng nên kiểm tra block có tồn tại hay không bằng lệnh block_given?
    Ví dụ:
        def tinhToan(a, b)
            puts "parameter của hàm tinhToan là #{a}, #{b}"
            yield(3, 4) if block_given?     # x = 3, y = 4
        end
        tinhToan(1, 2) { |x, y| print "tính toán của block: #{x} + #{y} = #{x + y}" }

## proc objects:

Khi viết một block, nếu muốn tái sử dụng code nhiều lần thì cần một đối tượng lưu nó lại để có thể gọi ra khi cần
    Ví dụ:
        myProc = Proc.new {|x| x * 2}
        print myProc.call(2)    # kết quả: 4
        [1, 2, 3].map(&myProc)  # tái sử dụng proc. Kết quả: [2, 4, 6]

## lambda:

Lambda là một function không có tên cụ thể, trả về một object => lambda là một object
    Lambda thực chất là 1 đối tượng của proc
    Lamdba nếu truyền thiếu tham số sẽ báo lỗi, còn proc nếu truyền thiếu tham số thì tham số bị thiếu đó sẽ có giá trị nil
    Ví dụ:
        result = lambda{|x| puts x + 1}
        puts  result.class      # Proc
        print result[1]         # 2
        print result.call(1)    # 2

## 
*** block và proc đem nguyên đoạn code chèn vào, còn lambda thì chỉ là 1 lời gọi hàm
    Ví dụ:
    def proc_math
        Proc.new { return 1 + 1 }.call
        return 2 + 2
    end
    def lambda_math
        lambda { return 1 + 1 }.call
        return 2 + 2
    end
    proc_math   # kết quả là 2. Vì proc bê nguyên đoạn code vào => gặp return -> dừng
    lambda_math # kết quả là 4. Vì nó chỉ là 1 lời gọi hàm bình thường. lambda hoạt động độc lập nên không ảnh hưởng tới toàn bộ khối lệnh chứa nó
