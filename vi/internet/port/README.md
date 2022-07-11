# PORT
- Thường được dùng chung theo địa chỉ IP với định dạng [Địa chỉ IP]:[Port]
- Ví dụng: 192.168.1.1:5000

## PORT PUBLIC
- 20, 21 : File Transfer Protocol (FTP) : Dùng share file.
- 22 : Secure Shell (SSH) : Dùng điều khiển từ xa cho máy tính hay server.
- 23 : Telnet : Dùng để kiểm tra port mạng cho các máy tính.
- 25 : Simple Mail Transfer Protocol (SMTP) : Cung cấp tính năng gửi mail SMTP trên máy tính.
- 53 : Domain Name Server (DNS) : Phân giải domain thành địa chỉ IP hoặc ngược lại.
- 67, 68 : Dynamic Host Configuration Protocol (DHCP) : Cung cấp địa chỉ IP động.
- 69 : Trivial File Transfer Protocol (TFTP) : Cung cấp đường truyền chuyển file.
- 80 : Hyper Text Transfer Protocol (HTTP) : Cung cấp văn bản text hoặc truy cập qua trình duyệt.
- 110 : Post Office Protocol (POP3) : Cung cấp tính năng gửi mail POP3 trên máy tính.
- 119 : Network News Transport Protocol (NNTP) : Chả biết dùng làm gì.
- 123 : Network Time Protocol (NTP) : Cung cấp thông tin giờ, đồng bộ thời gian.
- 135 - 139 : NetBIOS : Cung cấp tính năng điều khiển BIOS từ xa.
- 143 : Internet Message Access Protocol (IMAP4) : Cung cấp tinh năng gửi mail IMAP trên máy tính.
- 161, 162 : Simple Network Management Protocol (SNMP) : Cung cấp phương pháp quản lý mạng.
- 179 : Border Gateway Protocol (BGP) : Chắc liên quan gì đó đến gateway.
- 389 : Lightweight Directory Access Protocol : Không biết dùng làm gì.
- 443 : HTTP with Secure Socket Layer (HTTPS or SSL) : Cung cấp văn bản text hoặc truy cập qua trình duyệt với độ bảo mật cao.
- 500 : Internet Security Association and Key Management Protocol (ISAKMP) / Internet Key Exchange (IKE) : Cung cấp khóa bảo mật cho các phương thức dạng SSL.
- 636 : Lightweight Directory Access Protocol over TLS / SSL (LDAPS) : Không biết dùng làm gì.
- 989, 990 : FTP over TLS / SSL : Share file không dùng bảo mật.
- 1433 : Port mặc định cho kết nối đến database SQL Server.
- 3306 : Port mặc định cho kết nối đến dtabase MySQL hay MariaDB.
- 3389 : Port mặc định cho Remote Desktop của Windows.

## PORT ACTION
- Port hoạt động bằng cách xác định cổng cấp quyền cho dữ liệu được ra hay vào trong hệ thống máy tính trong mạng.
- Tất cả các thiết bị được kết nối mạng đều được trang bị các port được tiêu chuẩn hóa có số hiệu được ấn định.
- Những con số này được dành riêng cho một số giao thức nhất định và chức năng liên quan của chúng.
- Các port luôn được liên kết với địa chỉ IP của máy chủ cũng như các giao thức sử dụng cho việc giao tiếp trong mạng máy tính với nhau.
- Mỗi port được đặt tên bằng 1 số thứ tự nhất định và mỗi cổng sẽ phục vụ cho những dịch vụ cụ thể khác nhau nhằm mục đích cho phép các gói tin dễ dàng đến đúng nơi quy định.
- Bởi vì mục đích này mà các port có số thấp (từ 1024 trở xuống) thường được sử dụng cho các dịch vụ phổ biến từ trước đến nay.
- Còn các port có số cao hơn (từ 1024 trở lên) thì lại thường được sử dụng làm cổng tạm cho các dịch vụ ít phổ biến hơn.
- Để xác định lưu lượng đến nên được hướng đến giao thức nào, các số cổng khác nhau được sử dụng.
- Chúng cho phép một máy chủ lưu trữ với một địa chỉ IP duy nhất chạy các dịch vụ mạng.
- Mỗi số cổng có một dịch vụ riêng biệt và đối với mỗi máy chủ lưu trữ có thể có 65535 cổng cho mỗi địa chỉ IP.
- Tổ chức Internet Assigned Numbers Authority (IANA) chịu trách nhiệm quản lý việc sử dụng các cổng này.

## TÁC DỤNG

### Port mạng là chìa khóa, địa chỉ nhận diện tập tin, dữ liệu
- Giống như một người lính gác, số địa chỉ nhà ở, khi bạn đăng ký các loại port trên hệ thống máy tính của bạn sẽ giúp cho các tập tin được truy cập, được đưa vào đúng với địa chỉ port khớp với đầu bit tập tin đó.

### Port mạng có tác dụng chọn lọc tin
- Port sẽ quy định chỉ những tập tin nào mới được nhập vào máy và được thông qua xuất nhập trong hệ thống máy.
- Nếu như tập tin đúng với cổng bit thì sẽ được xâm nhập vào máy nhưng tất nhiên máy tính sẽ từ chối việc nhập dữ liệu nào đó nếu như không đúng cổng port.
- Điều này sẽ giúp phân loại và lựa chọn luôn những tập tin an toàn.

### Port mạng có tác dụng bảo vệ xâm nhập có hại cho máy tính
- Port cũng được xem là một trong những cổng bảo vệ an toàn cho máy tính.
- Port có thể phát hiện những tập tin xấu, có chứa virus làm ảnh hưởng đến các tập tin và máy tính.
- Nó sẽ loại bỏ những tập tin đó đi, loại bỏ virus xâm nhập, giúp máy tính luôn giữ được sự an toàn và đảm bảo tránh được những thông tin nhiễu.
- Port được xem là một cổng chìa khóa vô cùng quan trọng.

## PHÂN LOẠI

### Từ 0 đến 1023
- Các cổng từ 0 đến 1023 là các cổng nổi tiếng hoặc cổng hệ thống.

### Từ 1024 đến 49151
- 1024 đến 49151 là các cổng đã đăng ký được IANA chỉ định cho một dịch vụ cụ thể theo đơn của một thực thể yêu cầu.

### Từ 49152 đến 65535
- 49152 đến 65535 là các cổng động (riêng, cao) nằm trong khoảng từ 49,152 đến 65,535. Có thể được sử dụng cho mục đích tư nhân hoặc dịch vụ khách hàng hoặc tạm thời.

## CHECKING
- Các cách kiểm tra port mạng phổ biến:
    1. netstat : kiểm tra port mạng và IP đang kết nối trên máy tính.
    2. telnet <IP máy cần kiềm tra> <Port máy cần kiềm tra> : Kiểm tra một máy tính từ xa có thể kết nối qua 1 port được hay không.
    3. Ping <IP hoặc Domain máy cần kiềm tra> : Kiểm tra truy cập nhanh một máy hoặc check mạng máy tính.