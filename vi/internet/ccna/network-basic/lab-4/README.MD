# Lab 4 - Khôi phục mật khẩu cho router

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/lab-1-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả
- Trong bài lab này, chúng ta thực hiện các thao tác khôi phục mật khẩu cho router khi bị mất password đã cấu hình.

## Thực hiện
**Bước 1: Giả lập lỗi cấu hình sai mật khẩu**
Cấu hình một mật khẩu sai và lưu lại:
```console
Router(config)# hostname vnpro
vnpro(config)# enable password aksgiuwegi@123hui
vnpro(config)# exit
vnpro# wr
Building configuration...

[OK]
vnpro# exit
```

Lúc này chúng ta không thể đăng nhập vào router được nữa (Đăng nhập mật khẩu sai 3 lần):
```console
vnpro> enable
Password:
Password:
Password:
% Bad passwords

vnpro>
```

**Bước 2: Tắt/mở router**
Thực hiện tắt nguồn router, chờ khoảng 15s rồi mở lại router. Lưu ý: không được tắt rồi mở lại nhanh quá để tránh gây ra sự cố về nguồn điện.

**Bước 3: Sử dụng tổ hợp phím ngắt để đi vào rommon**
Trong quá trình router đang khởi động lại, sử dụng tổ hợp phím ngắt *"Ctrl + Break"* để đi vào mode rommon.
```console
System Bootstrap, Version 12.4(13r)T, RELEASE SOFTWARE (fcl)
Technical Support: http://www.cisco.com/techsupport
copyright (c) 2006 by cisco System, Inc.

Initializing memory for ECC
..
c2811 platform with 524288 Kbytes of main memory
Main memory is configured to 64 bit mode with ECC enabled
Readonly ROMMON initialized

< Nhấn "Ctrl + Break" tại đây >

rommon 1 >
```

**Bước 4: Đổi giá trị thanh ghi cấu hình**
Thực hiện đổi giá trị thanh ghi cấu hình thành 0x2142 rồi khởi động lại:
```console
rommon 1 > confreg 0x2142

You must reset or power cycle for new config to take effect
rommon 2 > reset
c2811 platform with 524288 Kbytes of main memory
Main memory is configured to 64 bit mode with ECC enabled
(...)
```

**Bước 5: Sửa mật khẩu**
Sau khi thay đổi giá trị thanh ghi cấu hình, router load vào một cấu hình trắng (blank), mật khẩu tại đây được bỏ qua khi khởi động. Thực hiện đi vào mode Privilege và load lại cấu hình cũ để sửa đổi mật khẩu:
```console
Router# copy startup-config running-config
Destination filename [running-config]?
1170 bytes copied in 0.284 secs (4120 bytes/sec)

vnpro# conf t
Enter configuration commands, one per line.  End with CNTL/Z.
vnpro(config)# enable password vnpro
vnpro(config)# end
vnpro# wr
Building configuration...
```

**Bước 6: Đổi lại giá trị thanh ghi cấu hình**
Thực hiện đổi lại giá trị thanh ghi cấu hình thành giá trị ban đầu là 0x2102 và khởi động lại để hoàn tất quá trình khôi phục mật khẩu:
```console
vnpro(config)# config-register 0x2102
vnpro(config)# end
vnpro# wr
Buidling configuration...
Jan  2 12:07:17.215: % SYS-5-CONFIG_I: Configured from console by console[OK]
vnpro# reload
```