# CONNECTION - Kết nối
- Connection là khái niệm kết nối chương trình tới những chương trình khác, những API, những service hay những database.
- Tại sao lại phải kết nối? Vì chúng ta muốn chương trình chúng ta có thêm data - dữ liệu để xử lý một số trường hợp hoặc một số hành động xử lý data mà chương trình chúng ta hiện tại không thể xử lý mà phải nhờ một chương trình khác xử lý dùm.
- Lưu ý khi sử dụng connection là hạn chế số lần gọi và số lần mở connection. Vì sao phải hạn chế? Vì nếu mở quá nhiều sẽ chiếm dụng quá nhiều dung lượng băng thông và gây nghẽn ở chương trình, API, service, database mà chúng ta gọi tới (Vì trên môi trường mạng thì mọi thứ đều có giới hạn của nó, khi chúng ta tới giới hạn thì có thể làm deadlock hệ thống).
- Lưu ý nữa khi sử dụng connection là dùng bao nhiêu thì lấy đúng bấy nhiêu, không lấy những thức không liên quan vì các yếu tố sau: lấy nhiều và dư sẽ làm đối tượng data của chúng ta lớn mà lớn thì chiếm băng thông nhiều => chậm, lấy dư thì làm các chương trình khác phải xử lý nhiều => tốn thời gian gây giảm hiệu năng. Lấy nhiều thì phải chờ lâu làm chương trình của mình sẽ chậm theo.

## DATA TYPE CONNECTION - Kiểu dữ liệu xử dụng cho connection
- Ngày nay những dữ liệu thường xử dụng cho connection có 4 dạng phổ biến :
    1. SOAP : là những gói dữ liệu kiểu XML (Đã có từ rất lâu).
    2. STREAM : là những gói dữ liệu kiểu BINARY (Dùng cho một đối tượng lớn như video, hình ảnh, ...).
    3. JSON : là những gói dữ liệu kiểu TEXT nhưng format theo kiểu JSON.
    4. GRPC : là những gói dữ liệu kiểu OBJECT, muốn xử dụng phải biết Object của nó là gì.

## APPLICATION CONNECTION - Kết nối các ứng dụng
- Kết nối kiểu ứng dụng là 1 dạng phổ biến ở thời kỳ đầu tiên của lập trình dựa trên ý tưởng lắng nghe và trả lời.
- Ý tưởng lắng nghe và trả lời gồm có 3 yếu tố:
    1. Ứng dụng lắng nghe : hay còn gọi là Host sẽ mở 1 port trên PC rồi từ đó lắng nghe các gói tin gửi đến Port này.
    2. Ứng dụng gửi gói tin : hay còn gọi là Client sẽ gửi 1 event tới 1 địa chỉ Host với thông tin yêu cầu kiểm tra Port, nếu OK thì gửi thông tin lên Host và chờ phản hồi.
    3. Ứng dụng trung gian : một số ứng dụng ở trên máy tính khác nhau có thể không gọi được trực tiếp đến nhau do không biết vị trí nên cần một ứng dụng trung gian gửi thông tin đi dùm.
- Đây là kiểu kết nối phổ biến trong các Game offline mà muốn dùng mạng máy tính để chơi chung với nhau. Sẽ có 1 máy làm host tức là trên máy đó, game sẽ mở Port để listen từ các máy khác trong mạng. Các máy khác sẽ connect vào và share chung data với nhau nhưng xử lý sẽ nằm ở từng máy.
- Bất lợi là khi một máy làm host mất kết nối hoặc tắt port hay tắt chương trình thì đồng thời các máy khác cũng không nhận được data dẫn đến out chương trình hay lỗi chương trình.
- Hiệu quả hoạt động của hệ thống và chương trình khi sử dụng cách này là trong 1 phạm vi nhỏ.
- Đối với .NET thì lập trình cho dạng kết nối này là Window Form hay Console.
- Những chương trình thường thấy sử dụng loại này là : Window Remote Desktop, Game Offline, VmWare, Virtual Box, Hyper-V, Docker, ...

## WEB CONNECTION - Kết nối web
- Kết nối Web là một kiểu có phần tương đương với Application Connection. Tức là vẫn có mở Port vẫn có lắng nghe.
- Điểm khác biệt là chúng sử dụng các kiểu dữ liệu theo quy chuẩn chung, truyền tín hiệu xa hơn và dồn được sức mạnh vào 1 máy tính (gọi là Server) để làm host -> những máy client sẽ kết nối ứng dụng ổ định hơn (tuy nhiên nguyên tắc là mất kết nối hay server tạch thì vẫn không lấy được data).
- Đối với .NET thì lập trình cho dạng kết nối này là Web MVC, Web API, Web Service, ...
- Những chương trình thường thấy là : Trang web, Game Online, VPN, Trình duyệt web (Chrome, Firefox, Cốc cốc), App điện thoại, App máy tính, Virus, ...