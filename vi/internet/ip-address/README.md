# IP ADDRESS
- Địa chỉ IP của 1 máy tính trên hệ thống mạng.
- Có 2 loại địa chỉ IP là v4 và v6.

## IPv4
- Là một dãy gồm 4 con số và ngăn cách nhau bằng dấu (.).
- Ví dụ: 1 địa chỉ IP là 192.168.1.1 gồm 4 con số là 192, 168, 1, 1.
- Địa chỉ IP được chia làm 4 lớp theo từng con số theo dấu (.) lần lượt là A.B.C.D.
- Giá trị tối thiểu của 1 con số là 0 và tối đa là 255.

### IP Class A
- Là những địa chỉ IP tính từ con số đầu. Được quy định là địa chỉ IP: 10.x.x.x là địa chỉ IP cho lớp mạng doanh nghiệp và không được dùng trong mạng internet.
- Ví dụ: trong công ty thì IP 10.0.0.1 dùng cho server A, còn IP 10.0.0.2 dùng cho server B.

### IP Class B
- Là những địa chỉ IP tính từ 2 con số đầu. Được quy định là địa chỉ IP: 192.168.x.x là địa chỉ IP cho lớp mạng cá nhân và không được dùng trên mạng internet.
- Ví dụ: trong một gia đình thì IP 192.168.1.1 dùng cho PC A, IP 192.168.1.2 dùng cho điện thoại B, IP 192.168.1.3 dùng cho TV C, ...

### IP Class C, D
- Là những địa chỉ IP tính từ 3 con số cho lớp C và hơn 3 con số cho lớp D.
- Ví dụ: trong 1 mạng wifi thì sẽ có cụm 192.168.1.x dùng cho wifi A và 192.168.2.x dùng cho wifi B.

## IPv6
- Có cấu trúc và thành phần gần giống như địa chỉ IPv4 nhưng có chiều dài nhiều hơn. Vì mục đích của nó là dùng đánh địa chỉ IP cho nhiều thiết bị trên mạng Internet hơn.
- IPv4 thì tối đa cấp được 4.3 tỷ IP còn IPv6 thì giới hạng này là : 2^128.
- Có định dạng là: 2001:0DB8:AC10:FE01:0000:0000:0000:0000.
- Là 1 dãy ký tự gồm 32 ký tự và được chia làm 4 ký tự là 1 cặp và được phân cách với nhau bằng dấu (:).
- 1 ký tự trong dãy có giá trị từ 0 đến 9 và vượt qua 9 thì đánh ký tự là A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.

## Những thông tin quan trọng trong 1 địa chỉ IP

### IP Address
- Là địa chỉ IP của máy tính cá nhân.

### Subnet mask
- Là địa chỉ mặt nạ mạng con theo tiêu chuẩn như 1 địa chỉ IP nhưng sẽ theo những con số là 2^n với n có giá trị từ 0 đến 8.
- 1 mạng máy tính bắt buộc phải có 1 subnet mask cho IPv4.
- Ví dụ: với lớp mạng A thì mặt nạ mạng con là 255.0.0.0 hay viết gọn là /8 (2^8 = 255)
- Ví dụ: với lớp mạng B thì mặt nạ mạng con là 255.255.0.0 hay viết gọn là /16 (2^16 = 2 * 2^8 = 255.255)
- Ví dụ: với lớp mạng C thì mặt nạ mạng con là 255.255.255.0 hay viết gọn là /24 (2^24 = 3 * 2^8 = 255.255.255)

### Default Gateway
- Là địa chỉ cổng mạng kết nối được đến Internet. Thường ghi nhận là IP của router wifi hay moderm.
- Cũng là 1 địa chỉ IP và thường sẽ lấy đi một địa chỉ trong lớp mạng để cấp cho nó.
- 1 mạng máy tính bắt buộc phải có 1 default gateway và nếu không có thì thiết bị đó chính là default gateway trong lớp mạng.
- 1 mạng máy tính có thể có nhiều hơn 1 default gateway.

### DNS
- Là địa chỉ IP của server có nhiệm vụ phân giải domain thành địa chỉ IP để người dùng truy cập,
- Ghi chú: Domain là đường dẫn đến 1 trang web hay một server trên thanh trình duyệt web.