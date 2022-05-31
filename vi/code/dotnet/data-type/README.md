# Datatype - Loại dữ liệu
- Loại dữ liệu là đơn vị cơ sở để xây dựng nên một chương trình.
- Loại dữ liệu là nơi định nghĩa dung lượng mà chương trình có thể sử dụng phần cứng máy tính, đặc biệt là RAM.
- Admin giới thiệu trước loại dữ liệu trước vì nếu không hiểu hay lạm dụng loại dữ liệu sẽ dấn đến chương trình ngốn nhiều RAM -> Gây lãn phí RAM, lãn phí CPU khi tính toán giá trị trên RAM (Thay vì chỉ cần 1 phần CPU nhỏ và 1 phần RAM nhỏ để tính toán 1 bài toán đơn giản không có số thực nhưng lại khai báo số thực làm phải tốn thêm CPU để tính toán dấu phẩy của phần thực và tốn RAM để lưu trữ -> Tăng độ phức tạp của bài toán).
- Có các loại dữ liệu căn bản sau :
| Thứ tự | Tên loại dữ liệu | Dung lượng | Mô tả                                                                           | Ưa dùng |
| :----: | :--------------- | :--------- | :------------------------------------------------------------------------------ | :-----: |
| 1      | nuint            | 4-8 bytes  | Dùng thay cho ulong và uint                                                     |         |
| 2      | nint             | 4-8 bytes  | Dùng thay cho long và int                                                       |         |
| 3      | ulong, UInt64    | 8 bytes    | Dùng cho số nguyên bắt đầu từ số 0 và giới hạn là 18 tỷ tỷ                      |         |
| 4      | long, Int64      | 8 bytes    | Dùng cho số nguyên bắt đầu từ âm 9 tỷ tỷ đến dương 9 tỷ tỷ                      | x       |
| 5      | uint, UInt32     | 4 bytes    | Dùng cho số nguyên bắt đầu từ số 0 và giới hạn là 4 tỷ                          |         |
| 6      | int, Int32       | 4 bytes    | Dùng cho số nguyên bắt đầu từ âm 2 tỷ đến dương 2 tỷ                            | x       |  
| 7      | ushort, UInt16   | 2 bytes    | Dùng cho số nguyên từ 0 đến 65,535                                              |         |
| 8      | short, Int16     | 2 bytes    | Dùng cho số nguyên từ -32,768 đến 32,767                                        |         |
| 9      | byte, UInt8      | 1 byte     | Dùng cho số nguyên từ 0 đến 255                                                 | x       |
| 10     | sbyte, Int8      | 1 byte     | Dùng cho số nguyên từ -128 đến 127                                              |         |
| 11     | float            | 4 bytes    | Kiểu số thực từ $±1.5 x 10^-45$ to $±3.4 x 10^384$ (6-9 chữ số sau dấu ',')     |         |
| 12     | double           | 8 bytes    | Kiểu số thực từ $±5.0 x 10^-324$ to $±1.7 x 10^308$ (15-17 chữ số sau dấu ',')  | x       |
| 13     | decimal          | 16 bytes   | Kiểu số thực từ $±1.0 x 10^-28$ to $±7.9228 x 10^28$ (28-29 chữ số sau dấu ',') | x       |
| 14     | bool             | 1 bit      | Kiểu đúng/sai, có/không hay bật/tắt                                             | x       |
| 15     | char             | 16 bit     | Dùng cho ký tự hoặc những bài toán liên quan đến bit, AND, OR                   |         |
| 16     | enum             | N/A        | Dùng khai báo 1 tập hợp tên được nối với 1 số xác định và không đổi             | x       |
| 17     | struct           | N/A        | Dùng khai báo 1 đối tượng chỉ để lưu trữ dữ liệu                                |         |
| 18     | class            | N/A        | Dùng như struct nhưng có thể khai báo thêm method để xử lý data                 | x       |
| 19     | null, ?          | 0 bit      | Dùng khai báo biến giá trị mà tại thời điểm sử dụng là không có data rỏ ràng    | x       |
| 20     | interface        | N/A        | Dùng khai báo 1 tập hợp hành động, method của 1 tập đối tượng                   | x       |
| 21     | string, String   | N/A        | Dùng khai báo 1 chuỗi ký tự và bản mã thường là UTF16                           | x       |
| 22     | var              | N/A        | Dùng khai báo 1 biến mà kiểu dữ liệu không rỏ được trả về từ 1 hàm, method      | x       |
| 23     | dynamic, object  | N/A        | Dủng khai báo 1 biến mà không biết kiểu dữ liệu                                 | x       |
| 24     | void             | N/A        | Dùng khai báo 1 hàm hay method không trả kết quả                                | x       |
| 25     | T                | N/A        | Dùng trong trường hợp đặc biệt sẽ được mô tả riêng                              |         |
| 26     | \[\], Array      | N/A        | Dùng cho tập hợp 1 kiểu dữ liệu lại thành 1 mảng                                | x       |
| 27     | List, IEnumable  | N/A        | Dùng cho tập hợp 1 kiểu dữ liệu lại thành 1 dãy có thứ tự                       | x       |
| 28     | Guid             | 32 bytes   | Dùng cho 1 đối tượng là 1 dãy ký tự đặt biệt                                    |         |
| 29     | Datetime         | 8 bytes    | Dùng cho lưu trữ ngày tháng và giờ chính xác đến nano second                    | x       |

##### Note
- Với các biến kiểu số nguyên thường được dùng trong bài toán đơn giản như cộng trừ hoặc lưu lại các bước của 1 đối tượng.
- Với các biến kiểu số thực thường được dùng trong bài toán nhân, chia vì sự phức tạp sau dấu phẩy và làm tròn giá trị.
- Nếu dùng kiểu số thực thì nên dùng double hoặc decimal vì float dùng 4 bytes để lưu trữ nên đôi khi việc làm tròn sẽ là vấn đề đau đầu.
- Với biến kiểu T dùng để ám chỉ không xác định loại dữ liệu cho biến đó và nếu muốn xử dụng phải đổi về object hoặc dùng các phương thức refactor để xử lý. Thường dùng cho việc khai báo 1 đối tượng có thể xử lý cho nhiều loại dự liệu.
- Tất cả các loại dữ liệu đều có thể quy đổi về loại dữ liệu object vì .NET là 1 ngôn ngữ lập trình OOP - Lập trình hướng đối tượng.
- Hạn chế dùng kiểu dữ liệu null vì sẽ tốn thêm dòng code if else để xử lý -> làm tăng độ phức tạp của chương trình hay hàm.
- Loại dữ liệu string, [], Array, List, IRnumable là những loại dữ liệu thường hay xài nhưng phải cẩn thận. Nếu được thì nên giới hạn độ dài của nó, còn không thì nên có những hàm xử lý lỗi cho chúng vì tính chất của chúng là loại dữ liệu có thể chứa vô hạn dung lượng hoặc null, tức là với 1 biến khai báo thì khi nhập data vào có thể overload RAM gây ra 1 số lỗi không mong muốn.
- Nếu được nên hạn chế dùng dynamic và object vì chúng khá rắc rối trong việc xác định loại dữ liệu và thay đổi hay đọc chúng.
- Nếu đã dùng kiểu dữ liệu bool thì đừng nên dùng thêm kiểu null nữa.
- Khuyến khích dùng class thay cho struct vì sau này muốn mở rộng thêm phương thức - method sẽ dễ hơn.