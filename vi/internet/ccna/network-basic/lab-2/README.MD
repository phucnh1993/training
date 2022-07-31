# Lab 2 - Cấu hình cơ bản trên router

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/lab-2-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả

- Bài lab bao gổm 1 router và 1 PC được kết nối bằng cáp mạng Ethernet và Console như hình vẽ.
- Trên sơ đồ lab này, chúng ta sẽ cấu hình cơ bản trên router.

## Yêu cầu

1. Kết nối giữa router và PC như được chỉ ra trên hình 1. Thực hiện đăng nhập vào router.
2. Thực hiện di chuyển giữa các mode của giao diện dòng lệnh.
3. Xóa cấu hình, khởi động lại router.
4. Đặt hostname cho router là *"vnpro"*.
5. Cấu hình enable password cho router là *"vnpro"*.
6. Cấu hình console password cho router là *"cisco"*.
7. Thực hiện mã hóa các password trong file cấu hình.
8. Đặt IP trên cổng của router và cổng của PC như hình 1. Ping kiểm tra.
9. Lưu cấu hình đã thực hiện.

## Thực hiện

**Bước 1: Kết nối router và PC**
Thực hiện đi dây kết nối PC và router theo như sơ đồ lab.

**Bước 2: Thực hiện di chuyển giữa các mode của giao diện dòng lệnh**
Sau khi khởi động thành công, màn hình sẽ hiển thị dòng thông báo yêu cầu nhấn *"Enter"* để tiếp tục:
```console
Router con0 is now available

Press RETURN to get started.
```

Sau khi thấy thông báo ở trên xuất hiện thì nhấn vào nút *"Enter"* trên bàn phím để đi vào User mode:
```console
Router>
```

Kế tiếp ta chuyển từ mode User sang mode Privilege:
```console
Router> enable
Router#
```

Di chuyển từ mode Privilege qua mode Config:
```console
Router# configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#
```

Vào sub-mode cấu hình trên cổng F0/0 của router (với con số 0 đầu là index cho card mạng thứ nhất và con số 0 thứ 2 là index cho cổng mạng thứ nhất của card mạng thứ nhất):
```console
Router(config)# interface fastEthernet 0/0
Router(config-if)#
```

**Note:** Một router có thể có nhiều card mạng và 1 card mạng có thể có nhiều cổng mạng. Tùy vào tốc độ cổng mạng mà ta sẽ có tên interface cổng mạng khác nhau, ở đây cổng mạng có tốc độ 100Mbps tương đương với fastEthernet.

Sử dụng các lệnh **"exit"** và **"disable"** để đi từ các mode bên trong ra ngoài:
```console
Router(config-if)# exit
Router(config)# exit
Router# disable
Router>
```

Hoặc có thể đi thẳng từ các sub-mode ra Privilege mode bằng cách nhấn tổ hợp phím **"Ctrl-Z"** hoặc đánh lệnh **"end"**:
```console
Router(config-if)# end
Router#
```

**Bước 3: Xóa cấu hình, khởi động lại router**
```console
Router# erase startup-config
Erasing the nvram filesystem will remove all configuration files! Continue?
[confirm] <- Nhấn Enter tại đây
[OK]
Erase of nvram: complete
Router#
Router# reload

Proceed with reload? [confirm] <- Nhấn Enter tại đây

*Feb 18 02:37:06/563:  %SYS-5-RELOAD:  Reload requested by console. Reload Reason: Reload Command.
```

Sau khi quá trình khởi động lại hoàn tất, dòng thông báo dưới đây sẽ hiện ra, ta chọn **"no"** và nhấn Enter:
```console
--- System Configuration Dialog ---
Would you like to enter the initial configuration dialog? [yes/no]: no
```

**Bước 4: Đặt hostname cho router**
```console
Router(config)# hostname vnpro
vnpro(config)#
```

**Bước 5: Cấu hình enable password vnpro**
```console
vnpro(config)# enable password vnpro
vnpro(config)#
```

Thực hiện kiểm tra bằng cách quay trở lại mode User rồi đi vào lại mode Privilege:
```console
vnpro(config)# exit
vnpro#
*Oct 26 03:11:50.343:  %SYS-5-CONFIG_I: Configured from console by console
vnpro# disable
vnpro>
vnpro> enable
Password: <- Nhập Password "vnpro", password sẽ không hiển thị trong quá trình nhập.
vnpro#
```

**Bước 6: Cấu hình console password**
```console
vnpro# configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
vnpro(config)# line console 0
vnpro(config-line)# password cisco
vnpro(config-line)# login
vnpro(config-line)# exit
vnpro(config)#
```

Thực hiện kiểm tra bằng cách thoát ra ngoài rồi nhấn **"Enter"** để đi vào User mode:
```console
vnpro# disable
vnpro> exit

vnpro con0 is now available
Press RETURN to get started. <- Nhấn Enter để đi vào User mode.

User Access Verification

Password: <- Nhập Password "cisco", password sẽ không hiển thị trong quá trình nhập.

vnpro>
```

**Bước 7: Mã hóa các password trong file cấu hình**
Kiểm tra hiện tại các password trong file cấu hình đã được mã hóa hay chưa:
```console
vnpro# show running-config
Building configuration...
(...)
enable password vnpro
(...)
line con 0
 password cisco
 login
line aux 0
line vty 0 4
 login
!
scheduler allocate 20000 1000
!
end
```

Thực hiện mã hóa các password:
```console
vnpro(config)# service password-encryption
```

Kiểm tra bằng cách xem lại file cấu hình:
```console
vnpro# show running-config
Building configuration...
(...)
!
enable password 7 104D000A0618
!
(...)
line con 0
 password 7 0701355C5D29485744
 logging synchronous
 login
line aux 0
line vty 0 4
 login
!
scheduler allocate 20000 1000
!
end
```

**Bước 8: Đặt IP trên các cổng router và PC**
Trên router:
```console
vnpro(config)# interface f0/0
vnpro(config-if)# no shutdown
vnpro(config-if)# ip address 192.168.1.1 255.255.255.0
vnpro(config-if)# exit
vnpro(config)#
```

Trên PC, chúng ta thực hiện cài đặt IP trên card mạng LAN có dây của PC là 192.168.1.2/24. Kiểm tra trên router:
```console
vnpro# show ip interface brief
Interface                  IP-Address         OK?  Method  Status                 Protocol
FastEthernet0/0            192.168.1.1        YES  unset   up                     up
FastEthernet0/1            unassigned         YES  unset   administratively down  down
```

Ping kiểm tra từ router xuống PC:
```console
vnpro# ping 192.168.1.2

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.1.2, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/6/10 ms
vnpro#
```

Ping kiểm tra từ PC lên router bằng cách sử dụng chương trình CMD bằng dòng lệnh **ping 192.168.1.1**

**Bước 9: Lưu cấu hình**
```console
vnpro# copy running-config startup-config
Destination filename [startup-config]? <- Nhấn Enter tại đây
Building configuration...
[OK]
vnpro#
```

Hoặc sử dụng lệnh **"write memory"** của mode Privilege:
```console
vnpro# write memory
Building configuration...
[OK]
vnpro#
```