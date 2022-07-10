# DHCP
- Là một máy chủ hay 1 thiết bị chạy ứng dụng có tên là DHCP.
- Ứng dụng DHCP này cung cấp tính năng quản lý và phân phối địa chỉ IP trong 1 lớp mạng.
- Thường phổ biến trong mạng LAN, Wifi, mạng gia đình, mạng doanh nghiệp.
- Nhằm quản lý và cấp tự động địa chỉ IP.
- Nếu số lượng địa chỉ được cấp đã đến giới hạn thì DHCP sẽ không cấp IP nữa mà sẽ chờ 1 địa chỉ IP nào đó hết hạn mà không được gia hạn sẽ tái sử dụng.
- Chỉ có thể có 1 thiết bị cung cấp DHCP trong 1 lớp mạng. Nếu có 2 cái trở lên sẽ gây rối loạn và cung cấp địa chỉ IP lung tung.
- Có thể vừa cung cấp địa chỉ IPv4 và IPv6.
- Nếu 1 hệ thống hay lớp mạng không có DHCP thì vẫn có thể sử dụng được nhưng người dùng phải dùng IP tĩnh (Setup 1 IP trong lớp mạng). Điều này sẽ gây khó khăn với người dùng mới vì không biết IP của subnet mask, default gateway và dns.