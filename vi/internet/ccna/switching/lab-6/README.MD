# Lab 6 - Static route

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/switching/image/lab-6-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả
- Sơ đồ lab gồm 3 router và 2 PC được đấu nối với nhau như hình 1.
- Trên sơ đồ này, chúng ta sẽ thực tập cấu hình các static route đảm bảo mọi địa chỉ trên sơ đồ thấy được nhau.

## Yêu cầu
1. Chúng ta thực hiện đấu nối vật lý cho các thiết bị và đặt địa chỉ IP cũng như các hostname của các router như được chỉ ra trên hình 1.
2. Sau khi thiết lập xong sơ đồ, chúng ta tiến hành cấu hình các static route trên các router đảm bảo mọi địa chỉ IP trên sơ đồ có thể đi đến được nhau.
3. Thực hiện các bước kiểm tra ping và trace route từ PC1 đến PC2 để kiểm tra kết quả cấu hình.

## Thực hiện
**Bước 1: Kết nối và cấu hình cơ bản**
Chúng ta thực hiện kết nối thiết bị và cấu hình cơ bản trên các thiết bị theo yêu cầu đặt ra.

**Bước 2: Cấu hình static route**
***Cấu hình***
R1 chưa có route đi đến các subnet 192.168.2.0/24, 192.168.23.0/24 và 192.168.3.0/24. Thực hiện cấu hình các static route đi đến các subnet này trên R1:
```console
R1(config)# ip route 192.168.2.0 255.255.255.0 192.168.12.2
R1(config)# ip route 192.168.23.0 255.255.255.0 192.168.12.2
R1(config)# ip route 192.168.3.0 255.255.255.0 192.168.12.2
```

R2 chưa có route đi đến các subnet 192.168.1.0/24 và 192.168.3.0/24. Thực hiện cấu hình các route đi đến các subnet này trên R2:
```console
R2(config)# ip route 192.168.1.0 255.255.255.0 192.168.12.1
R2(config)# ip route 192.168.3.0 255.255.255.0 192.168.23.3
```

R3 chưa có route đi đến các subnet 192.168.1.0/24, 192.168.12.0/24 và 192.168.2.0/24. Thực hiện cấu hình các route đi đến các subnet này trên R2:
```console
R3(config)# ip route 192.168.1.0 255.255.255.0 192.168.23.2
R3(config)# ip route 192.168.12.0 255.255.255.0 192.168.23.2
R3(config)# ip route 192.168.2.0 255.255.255.0 192.168.23.2
```

***Kiểm tra:***
Bảng định tuyến của các router:
```console
R1# show ip route static
S     192.168.23.0/24 [1/0] via 192.168.12.2
S     192.168.2.0/24 [1/0] via 192.168.12.2
S     192.168.3.0/24 [1/0] via 192.168.12.2
R2# show ip route static
S     192.168.1.0/24 [1/0] via 192.168.12.1
S     192.168.3.0/24 [1/0] via 192.168.23.3
R3# show ip route static
S     192.168.12.0/24 [1/0] via 192.168.23.2
S     192.168.1.0/24 [1/0] via 192.168.23.2
S     192.168.2.0/24 [1/0] via 192.168.23.2
```

Từ mỗi router đã đi đến được tất cả các subnet không kết nối trực tiếp với mình:
```console
R1# ping 192.168.2.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.2.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 4/53/76 ms

R1# ping 192.168.23.2
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.23.2, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 4/31/48 ms

R1# ping 192.168.3.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.3.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 44/55/64 ms

R2# ping 192.168.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 8/43/60 ms

R2# ping 192.168.3.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.3.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 16/31/60 ms

R3# ping 192.168.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 20/56/92 ms

R3# ping 192.168.12.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.12.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 32/61/88 ms

R3# ping 192.168.2.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.2.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 32/59/80 ms
```

**Bước 3: Ping và trace route**
Thực hiện ping từ PC1 đến PC2. *ping 192.168.3.1*
Thực hiện từ PC1 tracert đến PC2. *tracert 192.168.3.1*
Từ route R1 thực hiện trace route đến PC2
```console
R1# traceroute 192.168.3.2

Type escape sequence to abort.
Tracing the route to 192.168.3.2

  1 192.168.12.2 32 msec 32 msec 32 msec
  2 192.168.23.3 60 msec 44 msec 64 msec
  3 192.168.3.2 56 msec 76 msec 88 msec
```

**Cấu hình đầy đủ:**
**R1:**
```console
!
interface FastEthernet0/0
 ip address 192.168.1.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no shutdown
 ip address 192.168.12.1 255.255.255.0
 duplex auto
 speed auto
!
ip route 192.168.2.0 255.255.255.0 192.168.12.2
ip route 192.168.3.0 255.255.255.0 192.168.12.2
ip route 192.168.23.0 255.255.255.0 192.168.12.2
!
```

**R2:**
```console
!
interface Loopback0
 ip address 192.168.2.1 255.255.255.0
!
interface FastEthernet0/0
 ip address 192.168.12.2 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no shutdown
 ip address 192.168.23.2 255.255.255.0
 duplex auto
 speed auto
!
ip route 192.168.1.0 255.255.255.0 192.168.12.1
ip route 192.168.3.0 255.255.255.0 192.168.23.3
!
```

**R3:**
```console
!
interface FastEthernet0/0
 ip address 192.168.23.3 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no shutdown
 ip address 192.168.3.2 255.255.255.0
 duplex auto
 speed auto
!
ip route 192.168.1.0 255.255.255.0 192.168.23.2
ip route 192.168.2.0 255.255.255.0 192.168.23.2
ip route 192.168.12.0 255.255.255.0 192.168.23.2
!
```

## Câu hỏi ôn tập
1. Hãy phân biệt giữa định tuyến tĩnh (static routing) và định tuyến động (dynamic routing)?
2. Cho biết câu lệnh để kiểm tra các route connected hiện có trong bảng định tuyến.
3. Cho biết câu lệnh để kiểm tra các route static đã cấu hình trong bảng định tuyến.
4. Cho biết câu lệnh nguyên lý hoạt động của các tiện ích ping và trace.