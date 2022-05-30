# DOTNET
- Giới thiệu về ngôn ngữ lập tình .NET

## Datatype - Loại dữ liệu
- Loại dữ liệu là đơn vị cơ sở để xây dựng nên một chương trình.
- Loại dữ liệu là nơi định nghĩa dung lượng mà chương trình có thể sử dụng phần cứng máy tính, đặc biệt là RAM.
- Admin giới thiệu trước loại dữ liệu trước vì nếu không hiểu hay lạm dụng loại dữ liệu sẽ dấn đến chương trình ngốn nhiều RAM -> Gây lãn phí RAM, lãn phí CPU khi tính toán giá trị trên RAM (Thay vì chỉ cần 1 phần CPU nhỏ và 1 phần RAM nhỏ để tính toán 1 bài toán đơn giản không có số thực nhưng lại khai báo số thực làm phải tốn thêm CPU để tính toán dấu phẩy của phần thực và tốn RAM để lưu trữ -> Tăng độ phức tạp của bài toán).
- Có các loại dữ liệu căn bản sau :
| Thứ tự | Tên loại dữ liệu | dung lượng | Mô tả                                                                        |
| ------ | ---------------- | ---------- | ---------------------------------------------------------------------------- |
| 1      | nuint            | 4-8 bytes  | Dùng thay cho ulong và uint                                                  |
| 2      | nint             | 4-8 bytes  | Dùng thay cho long và int                                                    |
| 3      | ulong, UInt64    | 8 bytes    | Dùng cho số nguyên bắt đầu từ số 0 và giới hạn là 18 tỷ tỷ                   |
| 4      | long, Int64      | 8 bytes    | Dùng cho số nguyên bắt đầu từ âm 9 tỷ tỷ đến dương 9 tỷ tỷ                   |
| 5      | uint, UInt32     | 4 bytes    | Dùng cho số nguyên bắt đầu từ số 0 và giới hạn là 4 tỷ                       |
| 6      | int, Int32       | 4 bytes    | Dùng cho số nguyên bắt đầu từ âm 2 tỷ đến dương 2 tỷ                         |
| 7      | ushort, UInt16   | 2 bytes    | Dùng cho số nguyên từ 0 đến 65,535                                           |
| 8      | short, Int16     | 2 bytes    | Dùng cho số nguyên từ -32,768 đến 32,767                                     |
| 9      | byte             | 1 byte     | Dùng cho số nguyên từ 0 đến 255                                              |
| 10     | sbyte            | 1 byte     | Dùng cho số nguyên từ -128 đến 127                                           |
| 11     | float            | 4 bytes    | Kiểu số thực từ ±1.5 x 10^-45 to ±3.4 x 10^38 (6-9 chữ số sau dấu ',')       |
| 12     | double           | 8 bytes    | Kiểu số thực từ ±5.0 x 10^-324 to ±1.7 x 10^308 (15-17 chữ số sau dấu ',')   |
| 13     | decimal          | 16 bytes   | Kiểu số thực từ ±1.0 x 10^-28 to ±7.9228 x 10^28 (28-29 chữ số sau dấu ',')  |
| 14     | bool             | 1 bit      | Kiểu đúng/sai, có/không hay bật/tắt                                          |
| 15     | char             | 16 bit     | Dùng cho ký tự hoặc những bài toán liên quan đến bit, AND, OR                |
| 16     | enum             | N/A        | Dùng khai báo 1 tập hợp tên được nối với 1 số xác định và không đổi          |
| 17     | struct           | N/A        | Dùng khai báo 1 đối tượng chỉ để lưu trữ dữ liệu                             |
| 18     | class            | N/A        | Dùng như struct nhưng có thể khai báo thêm method để xử lý data              |
| 19     | null, ?          | 0 bit      | Dùng khai báo biến giá trị mà tại thời điểm sử dụng là không có data rỏ ràng |
| 20     | interface        | N/A        | Dùng khai báo 1 tập hợp hành động, method của 1 tập đối tượng                |
| 21     | string, String   | N/A        | Dùng khai báo 1 chuỗi ký tự và bản mã thường là UTF16                        |
| 22     | var              | N/A        | Dùng khai báo 1 biến mà kiểu dữ liệu không rỏ được trả về từ 1 hàm, method   |
| 23     | dynamic, object  | N/A        | Dủng khai báo 1 biến mà không biết kiểu dữ liệu                              |
| 24     | void             | N/A        | Dùng khai báo 1 hàm hay method không trả kết quả                             |
| 25     | T                | N/A        | Dùng trong trường hợp đặc biệt sẽ được mô tả riêng                           |

### Note
- Với các biến kiểu số nguyên thường được dùng trong bài toán đơn giản như cộng trừ hoặc lưu lại các bước của 1 đối tượng.
- Với các biến kiểu số thực thường được dùng trong bài toán nhân, chia vì sự phức tạp sau dấu phẩy và làm tròn giá trị.
- Với biến kiểu T dùng để ám chỉ không xác định loại dữ liệu cho biến đó và nếu muốn xử dụng phải đổi về object hoặc dùng các phương thức refactor để xử lý. Thường dùng cho việc khai báo 1 đối tượng có thể xử lý cho nhiều loại dự liệu.
- Tất cả các loại dữ liệu đều có thể quy đổi về loại dữ liệu object vì .NET là 1 ngôn ngữ lập trình OOP - Lập trình hướng đối tượng.
- Hạn chế dùng kiểu dữ liệu null vì sẽ tốn thêm dòng code if else để xử lý -> làm tăng độ phức tạp của chương trình hay hàm.