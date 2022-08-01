# Lab 5 - Sao lưu và nâng cấp IOS cho router

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/lab-5-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả
Trong bài lab này, chúng ta sẽ thực hiện:
- Sao lưu IOS trên router ra một host bên ngoài để dự phòng.
- Copy IOS từ một host vào router để nâng cấp IOS cho router.
- Load IOS cho router khi router bị mất IOS.
Việc sao chép dữ liệu giữa router và PC được thực hiện bằng cách sử dụng TFTP.

## Thực hiện
**Bước 1: Kết nối thiết bị**
Chúng ta thực hiện kết nối dây giữa router và PC rồi thực hiện đặt IP như được chỉ ra trên hình 1. Đảm bảo rằng PC và router thấy được nhau.

**Bước 2: Cài đặt phần mềm TFTP Server trên PC**
Trên PC thực hiện cài đặt phần mềm TFTPd32 để giả lập PC thành một TFTP Server. Phần mềm này có thể được download miển phí từ link [TFTPd32](http://tftpd32.jounin.net/). Giao diện của chương trình TFTPd32:
![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/tftpd32.jpg?raw=true)
<div align="center">
    Hình 2 - Giao diện chương trình TFTPd32.
</div>

Trên giao diện này, chúng ta thực hiện chỉnh sửa lại thư mục làm việc (mục "Current Directory") và địa chỉ server (mục "Server Interface") một cách thích hợp.

**Bước 3: Sao lưu IOS từ router ra PC**
Kiểm tra version BIOS đang được sửa dụng trên router:
```console
Router# show version
Cisco IOS Software, 2800 Software (C2800NM-ADVIPSERVICESK9-M), Version 12.4(15)T9,
RELEASE SOFTWARE (fc5)
Technical Support: http://www.cisco.com/techsupport
Copyright (c) 1986-2009 by Cisco Systems, Inc.
Compiled Tue 28-Apr-09 13:09 by prod_rel_team

ROM: System Bootstrap, Version 12.4(13r)T, RELEASE SOFTWARE (fc1)

Router uptime is 6 minutes
System returned to ROM by power-on
System image file is "flash:c2800nm-advipservicesk9-mz.124-15.T9.bin"
(...)
```

Thực hiện backup IOS này ra TFTP server (trước đó nhớ mở chương trình TFTPd32 trên PC và thực hiện các thiết lập thích hợp).
```console
Router# copy flash: tftp:
Source filename []? c2800nm-advipservicesk9-mz.124-15.T9.bin
Address or name of remote host []? 192.168.1.2
Destination filename [c2800nm-advipservicesk9-mz.124-15.T9.bin]?
.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
51432612 bytes copied in 195.348 secs (263287 bytes/sec)
```

**Bước 4: Copy IOS từ PC lên router**
Thực hiện copy file IOS từ PC (TFTP server) vào Flash của router. Thao tác này được thực hiện nhằm mục đích nâng cấp IOS cho router.
```console
Router# copy tftp: flash:
Address or name of remote host []? 192.168.1.2
Source filename[]? c2800nm-advipservicesk9-mz.124-15.T9.bin
Destination filename [c2800nm-advipservicesk9-mz.124-15.T9.bin]? <- Nhấn Enter
%Warning: There is a file already existing with this name
Do you want to over write? [confirm] <- Nhấn Enter để xác minh ghi đè
Accessing tftp://192.168.1.2/c2800nm-advipservicesk9-mz.124-15.T9.bin...
Loading     c2800nm-advipservicesk9-mz.124-15.T9.bin     from     192.168.1.2    (via
FastEthernet0/0):
.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
[OK - 51432612 bytes]

51432612 bytes copied in 205.944 secs (249741 bytes/sec)
```

**Bước 5: Load IOS cho router khi router bị mất IOS**
Thực hiện xóa IOS trên Flash của router rồi khởi động lại để giả lập tình huống mất ISO:
```console
Router# delete flash:c2800nm-advipservicesk9-mz.124-15.T9.bin
Delete filename [c2800nm-advipservicesk9-mz.124-15.T9.bin]?
Delete flash:c2800nm-advipservicesk9-mz.124-15.T9.bin? [confirm]
Router# reload
Proceed with reload? [confirm]

*Oct 17  03:33:13.711: %SYS-5-RELOAD: Reload requested by console. Reload Reason:
Reload Command.
```

Sau một vài lần kiểm tra IOS trong Flash không thành công, router đi vào chế độ rommon:
```console
System Bootstrap, Version 12.4(13r)T, RELEASE SOFTWARE (fcl)
Technical Support: http://www.cisco.com/techsupport
copyright (c) 2006 by cisco System, Inc.

Initializing memory for ECC
..
c2811 platform with 524288 Kbytes of main memory
Main memory is configured to 64 bit mode with ECC enabled


Readonly ROMMON initialized
program load complete, entry point: 0x9000f000, size: 0xcb80
program load complete, entry point: 0x8000f000, size: 0xcb80
loadprog: bad file magic number:      0x0
boot: cannot load "flash:"
c2811 platform with 524288 Kbytes of main memory
Main memory is configured to 64 bit mode with ECC enabled


Readonly ROMMON initialized
program load complete, entry point: 0x9000f000, size: 0xcb80
program load complete, entry point: 0x8000f000, size: 0xcb80
loadprog: bad file magic number:      0x0
boot: cannot load "flash:"
c2811 platform with 524288 Kbytes of main memory
Main memory is configured to 64 bit mode with ECC enabled


Readonly ROMMON initialized
rommon 1 >
```

Thực hiện các lệnh sau để khai báo các thông số cho hoạt động load IOS bằng rommon:
```console
rommon 3 > IP_ADDRESS=192.168.1.1 <- Địa chỉ IP sử dụng cho router
rommon 4 > IP_SUBNET_MASK=255.255.255.0 <- Subnet mask của IP router
rommon 5 > DEFAULT_GATEWAY=192.168.1.2 <- Sử dụng địa chỉ của TFTP server
rommon 6 > TFTP_SERVER=192.168.1.2 <- Địa chỉ của TFTP server
rommon 7 > TFTP_FILE=c2800nm-advipservicesk9-mz.124-15.T9.bin
rommon 8 > sync
```

Sau khi khai báo xong, thực hiện lệnh "tftpdnld" để bắt đầu tiến trình load IOS:
```console
rommon 9 > tftpdnld

          IP_ADDRESS: 192.168.1.1
      IP_SUBNET_MASK: 255.255.255.0
     DEFAULT_GATEWAY: 192.168.1.2
         TFTP_SERVER: 192.168.1.2
           TFTP_FILE: c2800nm-advipservicesk9-mz.124-15.T9.bin
        TFTP_VERBOSE: Process
    TFTP_RETRY_COUNT: 18
        TFTP_TIMEOUT: 7200
       TFTP_CHECKSUM: Yes
        TFTP_MACADDR: 00:1f:6c:6e:90:d0
             FE_PORT: Fast Ethernet 0
       FE_SPEED_MODE: Auto

Invoke this command for disaster recovery only.
WARNING: all existing data in all partitions on flash: will be lost!
Do you wish to continue? y/n:  [n]:  y <- Chọn "yes (y)"
.
Receiving c2800nm-advipservicesk9-mz.124-15.T9.bin from 192.168.1.2
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

(...)

File reception completed.
Validating checksum.
Copy file c2800nm-advipservicesk9-mz.124-15.T9.bin to flash:.
program load complete, entry point: 0x8000f000, size: 0xcb80

Format: All system sectors written. OK...
Format: Operation completed successfully.

Format of flash: complete
program load complete, entry point: 0x8000f000, size: 0xcb80

rommon 10 >
```

Sau khi load xong IOS, thực hiện khởi động lại router để hoàn tất quá trình:
```console
rommon 10 > reset
c2811 platform with 524288 Kbytes of main memory
Main memory is configured to 64 bit mode with ECC enabled
(...)
Self decompressing the image:
##############################################################################
#####################################################################################
############################ [OK]

(...)
Router>
```