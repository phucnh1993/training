# Datatype - Loại dữ liệu
- Loại dữ liệu là đơn vị cơ sở để xây dựng nên một chương trình.
- Loại dữ liệu là nơi định nghĩa dung lượng mà chương trình có thể sử dụng phần cứng máy tính, đặc biệt là RAM.
- Admin giới thiệu trước loại dữ liệu trước vì nếu không hiểu hay lạm dụng loại dữ liệu sẽ dấn đến chương trình ngốn nhiều RAM -> Gây lãn phí RAM, lãn phí CPU khi tính toán giá trị trên RAM (Thay vì chỉ cần 1 phần CPU nhỏ và 1 phần RAM nhỏ để tính toán 1 bài toán đơn giản không có số thực nhưng lại khai báo số thực làm phải tốn thêm CPU để tính toán dấu phẩy của phần thực và tốn RAM để lưu trữ -> Tăng độ phức tạp của bài toán).

## Sơ đồ tóm tắt loại dữ liệu
![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/code/dotnet/data-type/image/data-type-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ loại dữ liệu.
</div>

##### Nguyên lý hoạt động
- Mọi kiểu dữ liệu đều xuất phát từ kiểu dữ liệu nguyên thủy là Object - Đối tượng.
- Dựa vào đặc tính trạng thái của Object ta có 5 loại cơ bản là:
  1. undefine : là object chưa được định nghĩa.
  2. null : là object chưa được định nghĩa hoặc đã định nghĩa nhưng không có giá trị.
  3. boolean : là object đã được định nghĩa chỉ chứa 1 trong 2 giá trị duy nhất có dạng là true/false.
  4. number : là object đã được định nghĩa chứa 1 con số bất kỳ.
  5. string : là object được định nghĩa chứa 1 chuỗi ký tự đại diện cho 1 text.
- Trong kiều number thì ta có 2 loại chính là số thực và số nguyên.
- Tại sao lại phải phân biệt? Vì ta muốn cùng 1 dữ liệu thì số thực sẽ phức tạp hơn số nguyên.
- Tại sao phải phân biệt số âm hay không âm? Vì để biểu diễn 1 số âm hay không ta sẽ bị mất 1 bit để định nghĩa (làm mất 1 lượng lớn giá trị).

## Những loại dữ liệu thường thấy trong DOTNET

##### Có các loại dữ liệu căn bản sau :
| Tên loại dữ liệu | Dung lượng | Mô tả                                                                                   |
| ---              | ---        | ---                                                                                     |
| nuint            | 4-8 bytes  | Dùng thay cho ulong và uint.                                                            |
| nint             | 4-8 bytes  | Dùng thay cho long và int.                                                              |
| ulong, UInt64    | 8 bytes    | Dùng cho số nguyên bắt đầu từ số 0 và giới hạn là 18 tỷ tỷ.                             |
| long, Int64      | 8 bytes    | Dùng cho số nguyên bắt đầu từ âm 9 tỷ tỷ đến dương 9 tỷ tỷ.                             |
| uint, UInt32     | 4 bytes    | Dùng cho số nguyên bắt đầu từ số 0 và giới hạn là 4 tỷ.                                 |
| int, Int32       | 4 bytes    | Dùng cho số nguyên bắt đầu từ âm 2 tỷ đến dương 2 tỷ.                                   |
| ushort, UInt16   | 2 bytes    | Dùng cho số nguyên từ 0 đến 65,535.                                                     |
| short, Int16     | 2 bytes    | Dùng cho số nguyên từ $-32,768$ đến 32,767.                                             |
| byte, UInt8      | 1 byte     | Dùng cho số nguyên từ 0 đến 255.                                                        |
| sbyte, Int8      | 1 byte     | Dùng cho số nguyên từ $-128$ đến 127.                                                   |
| float            | 4 bytes    | Kiểu số thực từ $±1.5 * 10^{-45}$ to $±3.4 * 10^{384}$ (6-9 chữ số sau dấu ',').        |
| double           | 8 bytes    | Kiểu số thực từ $±5.0 * 10^{-324}$ to $±1.7 * 10^{08}$(15-17 chữ số sau dấu ',').       |
| decimal          | 16 bytes   | Kiểu số thực từ $±1.0 * 10^{-28}$ to $±7.9228 * 10^{28}$ (28-29 chữ số sau dấu ',').    |
| bool             | 1 bit      | Kiểu đúng/sai, có/không hay bật/tắt.                                                    |
| char             | 16 bit     | Dùng cho ký tự hoặc những bài toán liên quan đến bit, AND, OR.                          |
| enum             | unknow     | Dùng khai báo 1 tập hợp tên được nối với 1 số xác định và không đổi.                    |
| struct           | unknow     | Dùng khai báo 1 đối tượng chỉ để lưu trữ dữ liệu.                                       |
| class            | unknow     | Dùng như struct nhưng có thể khai báo thêm method để xử lý data.                        |
| null, ?          | 0 bit      | Dùng khai báo biến giá trị mà tại thời điểm sử dụng là không có data rỏ ràng.           |
| interface        | unknow     | Dùng khai báo 1 tập hợp hành động, method của 1 tập đối tượng.                          |
| string, String   | unknow     | Dùng khai báo 1 chuỗi ký tự và bản mã thường là UTF16.                                  |
| var              | unknow     | Dùng khai báo 1 biến mà kiểu dữ liệu không rỏ được trả về từ 1 hàm, method.             |
| dynamic, object  | unknow     | Dủng khai báo 1 biến mà không biết kiểu dữ liệu.                                        |
| void             | unknow     | Dùng khai báo 1 hàm hay method không trả kết quả.                                       |
| T                | unknow     | Dùng trong trường hợp đặc biệt sẽ được mô tả riêng.                                     |
| \[\], Array      | unknow     | Dùng cho tập hợp 1 kiểu dữ liệu lại thành 1 mảng.                                       |
| List, IEnumable  | unknow     | Dùng cho tập hợp 1 kiểu dữ liệu lại thành 1 dãy có thứ tự.                              |
| Guid             | 32 bytes   | Dùng cho 1 đối tượng là 1 dãy ký tự đặt biệt.                                           |
| Datetime         | 8 bytes    | Dùng cho lưu trữ ngày tháng và giờ chính xác đến nano second.                           |

##### Quá khó nhớ?
- Nếu thấy quá khó nhớ thì ta nhớ căn bản như sau: kiểu số nguyên thì cứ dùng int và kiểu số thực dùng float. Sau này nếu cần loại dữ liệu đặc biệt hơn thì ta cập nhật thêm.
- Hạn chế dùng null trong DotNet vì nó sẽ làm phát sinh thêm 1 điều kiện để kiểm tra dữ liệu.
- Khi ta khai báo 1 struct hay 1 class thì ta đã tạo thêm 1 data type.

##### Note
- Với các biến kiểu **số nguyên** thường được dùng trong bài toán đơn giản như cộng trừ hoặc lưu lại các bước của 1 đối tượng.
- Với các biến kiểu **số thực** thường được dùng trong bài toán nhân, chia vì sự phức tạp sau dấu phẩy và làm tròn giá trị.
- Nếu dùng kiểu **số thực** thì nên dùng **double** hoặc **decimal** vì **float** dùng *4 bytes* để lưu trữ nên đôi khi việc làm tròn sẽ là vấn đề đau đầu.
- Với biến kiểu T dùng để ám chỉ không xác định loại dữ liệu cho biến đó và nếu muốn xử dụng phải đổi về object hoặc dùng các phương thức refactor để xử lý. Thường dùng cho việc khai báo 1 đối tượng có thể xử lý cho nhiều loại dự liệu.
- Tất cả các loại dữ liệu đều có thể quy đổi về loại dữ liệu object vì .NET là 1 ngôn ngữ lập trình OOP - Lập trình hướng đối tượng.
- Hạn chế dùng kiểu dữ liệu null vì sẽ tốn thêm dòng code if else để xử lý -> làm tăng độ phức tạp của chương trình hay hàm.
- Loại dữ liệu string, [], Array, List, IRnumable là những loại dữ liệu thường hay xài nhưng phải cẩn thận. Nếu được thì nên giới hạn độ dài của nó, còn không thì nên có những hàm xử lý lỗi cho chúng vì tính chất của chúng là loại dữ liệu có thể chứa vô hạn dung lượng hoặc null, tức là với 1 biến khai báo thì khi nhập data vào có thể overload RAM gây ra 1 số lỗi không mong muốn.
- Nếu được nên hạn chế dùng dynamic và object vì chúng khá rắc rối trong việc xác định loại dữ liệu và thay đổi hay đọc chúng.
- Nếu đã dùng kiểu dữ liệu bool thì đừng nên dùng thêm kiểu null nữa.
- Khuyến khích dùng class thay cho struct vì sau này muốn mở rộng thêm phương thức - method sẽ dễ hơn.
- Có 5 dạng data type chính thường thấy là: number, string, array, object, null.
    1. number : thường là data type dùng lưu số, sẽ fix dung lượng byte và dễ sử dụng, mục đích phục vụ việc tính toán và giới hạn dung lượng.
    2. string : là data type dùng để lưu các đoạn text, dung lượng không cố định và có tính chất tương tự như 1 array, quan trọng là ký tự được mã hóa theo loại mã nào (UTF8, UTF16, ASCII, Unicode, ...).
    3. array : là data type dạng chuỗi hay còn gọi là 1 mảng. Dùng lưu trữ 1 dãy đối tượng có cùng kiểu dữ liệu. Quan trọng là những hàm phục vụ mục đích như tìm kiếm, thay thế, thêm, chèn, xóa, kiểm tra tồn tại, đếm, ... 1 đối tượng. Dung lượng có thể xác định.
    4. object : là data type được định nghĩa từ 1 đối tượng, hàm ý rằng đây là 1 loại data type có rất nhiều thuộc tính, dung lượng không xác định. Bất kỳ đối tượng khai báo dạng class hay struct đều có thể làm data type.
    5. null : là data type cho phép thêm loại giá là null vào trong 1 trường của đối tượng hay gán chính đối tượng đó bằng null. Là loại data type khó chịu nhất vì khi sử dụng chúng ta sẽ tốn thêm 1 câu lệnh if để check giá trị null. Ngoài ra data type này dùng để hàm ý là đối tượng hoặc trường giá trị của đối tượng đó là không xác định hoặc tại thời điểm sử dụng chúng vẫn chưa được khởi tạo hay gán giá trị.