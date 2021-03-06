# Lab 1 - Đăng nhập vào giao diện dòng lệnh của router

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/lab-1-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả

- Bài lab gồm 1 router và 1 PC được kết nối với nhau bằng cáp Console.
- Trong bài lab này, sẽ thực hiện truy cập vào giao diện dòng lệnh của router Cisco.

## Thực hiện

**Bước 1: Kết nối thiết bị**
Chúng ta thực hiện kết nối PC đến thiết bị bằng cáp console như hình vẽ 1.

**Bước 2: Cài đặt chương trình giao tiếp với router**
Chúng ta sử dụng phần mềm PuTTY để truy cập thiết bị. Phần mềm có thể tãi miễn phí từ trang web [Link download](https://www.putty.org).
PuTTY không cần cài đặt và có thể chạy trực tiếp từ máy tính.

![Picture_2](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/putty-start.jpg?raw=true)
<div align="center">
    Hình 2 - Giao diện chương trình PuTTY.
</div>

**Bước 3: Xác định cổng COM được sử dụng trên PC**
Click chuột phải vào My Computer hoặc This PC -> Chọn Manager.

![Picture_3](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/window-manager.jpg?raw=true)
<div align="center">
    Hình 3 - Chọn Manager.
</div>

Trong màn hình *"Computer Manager"* -> Chọn *"Device Manager"* ở ô bên trái và click chọn *"Ports (COM & LPT)"* ở ô bên phải

![Picture_4](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/device-com.jpg?raw=true)
<div align="center">
    Hình 4 - Xác định cổng COM.
</div>

Tại màn hình *Computer Manager* ta xác định được cổng COM được sử dụng trên PC và tại đây là cổng COM3.

**Bước 4: Thiết lập PuTTY**
Mở chương trình PuTTY đã cài trên PC và thực hiện chọn mục *"Serial"* và các thiết lập tương ứng như được chỉ ra trong hình bên dưới. Trong đó:
  1. Mục *"Serial line"*, nhập vào giá trị cổng COM đã được xác định ở bước trước, đó là cổng *"COM3"*.
  2. Trong mục *"Speed"*, để nguyên giá trị là 9600.

![Picture_5](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/putty-serial.jpg?raw=true)
<div align="center">
    Hình 5 - Thiết lập chương trình PuTTY.
</div>

Sau khi thiết lập xong, thực hiện nhấn *"Open"*, cửa sổ đăng nhập thiết bị sẽ hiện ra. Tại đăng ta sẽ nhập lệnh thao tác trên thiết bị.
