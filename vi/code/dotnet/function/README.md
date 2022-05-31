# FUNCTION - Hàm
- Có 2 loại hàm thường thấy là hàm nẳm trong 1 đối tượng (Method) hay hàm nằm ngoài 1 đối tượng (Function).
- Vì vậy ta có 2 loại lập trình thường thấy là lập trình hàm và lập trình hướng đối tượng.
- Lập trình hàm thì tự do hơn, tất cả đều được gói gọn và kế thừa trong 1 hàm.
- Lập trình hướng đối tượng thì bị bó buộc trong hoặc theo 1 đối tượng.
- Ta có thể hiểu hàm là tổng kết của 1 hành động dùng xử lý 1 số đối tượng dữ liệu.

## STRUCT - Cấu trúc
- Trong 1 hàm hay phương thức luôn bao gồm 6 yếu tố sau :
    1. Cấp độ truy cập : public, protected hay private là những cấp độ mà các hàm hay đối tượng có thể truy cập.
    2. Dữ liệu trả về : là loại dữ liệu hay đối tượng mà 1 hàm trả về sau khi xử lý xong, với void thì không trả về bất cứ gì hoặc 1 hay nhiều đối tượng trả về sẽ được khai báo rõ trước tên hàm.
    3. Tên hàm : là tên mà toàn bộ chương trình sẽ hiểu đó là 1 hàm và đặt theo nguyên tắc camel case hoặc capper case là chủ yếu. Với quy định là ký tự đầu tiên không phải là số và ký tự đặc biệt (tức là nó phải là chữ cái latin hoặc dấu gạch dưới).
    4. Biến truyền vào : là phần nằm trong dấu ngoặc tròn, có thể không khai báo nếu hàm nằm trong 1 đối tượng thì ta sẽ lấy dữ liệu từ con trỏ this hoặc tên biến của đối tượng, còn lại thì nếu hàm nằm bên ngoài đối tượng thì phải khai báo. Có 2 loại biến truyền vào là loại biến truyền vào không thay đổi giá trị và biến truyền vào sẽ thay đổi giá trị.
    5. Thân hàm : là nơi chứa những đoạn code xử lý dữ liệu được bao bọc trong ngoặc kép đối với DOTNET còn ngôn ngữ khác không có ngoặc kép thì không bàn tới.
    6. Loại dữ liệu không xác định : do 1 số hàm sẽ có biến truyền vào hay biến trả về hay xử lý đặc thù cho 1 đối tượng là 1 kiểu dữ liệu không xác định thì sẽ khai báo thêm phần này, phần này nằm trong ngoặc nhọn sau tên hàm.
- Công thức : <access_level> <return_value> <function_name><<temporary>>([this]<parameter>[= null]) {<function_body>}
- access_level : cấp độ truy cập (public, protected, private).
- return_value : giá trị trả về (void , int, string, List, ...).
- function_name : tên hàm (_add, sub, Check).
- parameter : biến truyền vào (int a, float b, out string x).
- function_body : thân hàm (int c = a + b; return c;).
- temporary : Loại dữ liệu không xác định (<T>, <TEnum>).
- [this] : trỏ tới biến gắn hàm vào (int a; a.function_name(this int a);)
- [= null] : biến truyền vào có dữ liệu mặc định không? Nếu có là gì? Default là null hoặc default của loại dữ liệu đó.

## NOTE - Ghi chú
- Khi viết unit test thì ta sẽ viết 1 hàm để kiểm tra 1 hàm với tập hợp các case có thể xảy ra trong 1 hàm với số lượng nhiều nhất.
- Hàm nên viết đơn giản và không dài hơn 20 dòng, nếu dài hơn 20 dòng thì nếu có thời gian ta nên tách nó ra.
- Trong 1 hàm không nên có nhiều hơn 15 chổ có từ khóa if, else, switch, case, default, for, while, where, firstOrDefault, any, count, try-catch. Vì số lượng các từ khóa này càng nhiều thì hàm càng phức tạp -> khả năng xảy ra lỗi mà không handle được là rất nhiều.
- Số lượng điều kiện so sánh trong 1 hàm cũng không nên nhiều hơn 15 do sẽ tạo nên 1 tổ hợp case xử lý rất phức tạp.
- Nên có comment cho 1 hàm ghi rõ công dụng của hàm.
- Nếu số lượng biến truyền vào lớn hơn 7 thì ta nên gom nó thành 1 object để nhìn hàm đỡ rối.
- 1 dòng trong hàm không nên vược quá 80 ký tự vì nhìn nó rất rối do có quá nhiều thông tin.
- Nếu trả về nhiều hơn 1 giá trị thì nên khai báo 1 đối tượng trả về cho hàm.
- Đặt tên hàm nên rõ nghĩa và đừng viết hoa hay viết thường hết tên hàm nếu viết dính liền (ADDALLOBJECT, addallobject) vì sẽ gây khó nhìn và khó kiểu, nên viết gọn gàn và quy tắc (addAllObject cho access level là private và AddAllObject cho access level là public).
- Admin ưa thích dùng public cho hàm vì tính dễ viết unit test của nó còn mọi người thích private cho hàm thì không sao.