# Lab 3 - CDP, Telnet

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/network-basic/image/lab-3-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả
  - Bài lab gồm hai router và một PC được đấu nối với nhau như hình 1.
  - Trên bài lab này, ta sẽ thực hiện hiển thị thông tin CDP và thực hiện cấu hình telnet trên các router.

## Yêu cầu
  1. Chúng ta thực hiện đấu nối dây giữa các router và PC rồi thực hiện đặt địa chỉ IP trên các thiết bị như được chỉ ra trên hình 1.
  2. Thực hiện các lệnh **"show cdp..."** trên các router để quan sát thông tin về router trên các thiết bị lân cận khác.
  3. Thực hiện cấu hình telnet trên các router và kiểm tra kết quả cấu hình bằng cách telnet từ PC đến router R1 và telent giữa 2 router đến nhau.

## Thực hiện
**Bước 1: Đấu nối dây và cấu hình ban đầu**
Chúng ta thực hiện kết nối dây giữa các thiết bị như hình 1. Thực hiện cấu hình cơ bản trên các router và đặt địa chỉ IP theo như hình vẽ.

**Bước 2: Thao tác với CDP**
Từ R1 xem thông tin về thiết bị lân cận:
```console
R1# show cdp neighbors
Capability Codes: R - Router, T - Trans Bridge, B - Source Route Bridge
                  S - Switch, H - Host, I - IGMP, r - Repeater, P - Phone,
                  D - Remote, C - CVTA, M - Two-port Mac Replay

Device ID        Local Intrfce    Holdtme    Capability  Platform   Port ID
R2               Fas 0/1          164        R S I       2811       Fas 0/1
```

Các thông tin nhận được:
  - Thiết bị lân cận có hostname là R2 (cột Device ID).
  - R1 sử dụng cổng F0/1 để đấu nối đến lân cận (cột Local Intrfce).
  - Lân cận là một router 2811 (cột Platform).
  - Lân cận sử dụng cổng F0/1 của nó để đấu nối đến router đang setup R1 (cổng Port ID).

Có thể xem thông tin chi tiết hơn bằng lệnh *"show cdp neighbor detail"* hoặc *"show cdp entry*"*:
```console
R1# show cdp neighbors detail
--------------------------
Device ID: R2
Entry address(es):
  IP address: 192.168.12.2
Platform: Cisco 2811, Capabilities: Router Switch IGMP
Interface: FastEthernet0/1,  Port ID (outgoing port): FastEthernet0/1
Holdtime : 174 sec

Version :
Cisco IOS Software, 2800 Software (C2800NM-ADVENTERPRISEK9-M), Version 12.4(15)T5,
RELEASE SOFTWARE (fc4)
Technical Support: http://www.cisco.com/techsupport
Copyright (c) 1986-2008 by Cisco Systems, Inc.
Compiled Wed 30-Apr-08 14:17 by prod_rel_team

advertisement version: 2
VTP Management Domain: ''
Duplex: full
```

Các lệnh này cho biết thêm các thông tin khác về thiết bị lân cận R2 bên cạnh thông tin nhận được từ lệnh *"show cdp neighbor"* ở trên:
  - Địa chỉ IP của R2 là: 192.168.12.2
  - Hệ điều hành R2 sử dụng là *"C2800NM-ADVENTERPRISEK9-M, Version 12.4(15)T5"*.
Trên R2 có thể thực hiện các lệnh *"show cdp..."* một cách tương tự.

**Bước 3: Cấu hình Telnet**
Cấu hình Telnet trên các router R1 và R2:
```console
R1-2(config)# enable password vnpro
R1-2(config)# line vty 0 4
R1-2(config-line)# password cisco
R1-2(config-line)# login
R1-2(config-line)# end
```

***PC telnet đến R1***
Thực hiện telnet từ PC đến R1 bằng cách sử dụng lệnh *"telnet 192.168.1.1"* trên dấu nhắc hệ thống của cửa sổ CMD. Cửa sổ telnet hiện ra, nhập các password để đi vào mode Privilege của router, tại đây ta có thể thực hiện các lệnh trên router giống như với truy cập qua console.

***Chú ý:*** Hệ điều hành Window có thể tắt dịch vụ Telnet Client ở mặc định. Nếu không thực hiện Telnet được, hãy bật dịch vụ Telnet client trên Window bằng cách mở **Control Panel** -> **Program** -> **Program and Features**, chọn *"Turn Windows features on or off"*. Trong cửa sổ hiện ra danh mục những feature, kéo xuống tìm mục *"Telnet Client"* và check vào ô này.

***Telnet từ router đến router***
Từ R2 telnet đến R1:
```console
R2# telnet 192.168.12.1
Trying 192.168.12.1 ... Open

User Access Verification

Password:
R1> enable
Paswword:
R1#
```

Trên R1 thực hiện xem danh sách các host đang telnet đến R1:
```console
R1# show users
    Line        User      Host(s)            Idle        Location
*  0 con 0                idle               00:00:00
 514 vty 0                idle               00:01:59 192.168.12.2
 515 vty 1                idle               00:02:31 192.168.1.2

  Interface     User            Mode         Idle     Peer Address
```

Hiện có 3 user truy cập vào R1: một user qua cổng console và hai user khác telnet qua các cổng VTY 0 (router 192.168.12.2) và VTY 1 (PC 192.168.1.2). Có thể ngắt kết nối của các user này bằng lệnh *"clear line..."*:
```console
R1# clear line 514 <- 514 là giá trị định danh cho session telnet từ R2
[confirm] <- Nhấn Enter tại đây
[OK]
```

Quan sát trên màn hình console của R2 đề thấy rằng R2 đã bị ngắt kết nối telnet đến R1:
```console
R1>
[Connection to 192.168.12.1 closed by foreign host]
R2#
```

Từ R1 thực hiện telnet đến R2:
```console
R1# telnet 192.168.12.2
Trying 192.168.12.2 ... Open

User Access Verification

Password:
R2> enable
Password:
R2#
```

Có thể từ màn hình telnet R2 trở lại màn hình cấu hình của R1 mà không cần ngắt kết nối telnet bằng cách sử dụng tổ hợp phím *"Ctrl + Shift + 6"* rồi nhấn phím *"X"*:
```console
R2# <Ctrl + Shift + 6 -> X>

R1#
```

Thực hiện tạo thêm một kết nối telnet nữa từ R1 đến R2:
```console
R1# telnet 192.168.12.2
Trying 192.168.12.2 ... Open
User Access Verification
Password:
R2>
```

Trở lại R1 bằng *"Ctrl + Shift + 6"* -> *"X"* và thực hiện kiểm tra bằng từ R1 hiện có hai kết nối telnet đến R2 bằng lệnh *"show session"*:
```console
R1# show sessions
Conn Host            Address            Byte  Idle Conn Name
   1 192.168.12.2    192.168.12.2          0     2 192.168.12.2
*  2 192.168.12.2    192.168.12.2          0     2
```

R1 có thể ngắt đi một kết nối từ nó đến R2 bằng lệnh *"disconnect..."*:
```console
R1# disconnect 1
Closing connection to 192.168.12.2 [confirm]
```

Kiểm tra lại bằng R1 chỉ còn một kết nối telnet đến R2:
```console
R1# show sessions
Conn Host            Address            Byte  Idle Conn Name
*  2 192.168.12.2    192.168.12.2          0     1
```