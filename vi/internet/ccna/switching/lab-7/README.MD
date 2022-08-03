# Lab 7 - Dự phòng đường đi với static route

## Sơ đồ

![Picture_1](https://github.com/phucnh1993/training/blob/master/vi/internet/ccna/switching/image/lab-7-diagram.jpg?raw=true)
<div align="center">
    Hình 1 - Sơ đồ bài lab.
</div>

## Mô tả
- Bài lab gồm 2 router được đấu nối với nhau như hình 1.
- Trên sơ đồ này, chúng ta thực hiện cấu hình dự phòng đường đi với kỹ thuật static route.

## Yêu cầu
1. Chúng ta thực hiện đấu nối các thiết bị và đặt địa chỉ IP theo sơ đồ được chỉ ra trên hình 1.
2. Chúng ta cấu hình dự phòng với static route đảm bảo:
    - R1 đi đến loopback của R2 theo link nối giữa hai cổng F0/0, link nối giữa hai cổng F0/1 chỉ để dự phòng.
    - R2 đi đến loopback của R1 theo link nối giữa hai cổng F0/1, link nối giữa hai cổng F0/0 chỉ để dự phòng.

## Thực hiện
**Bước 1: Đấu nối thiết bị và đặt IP**
Chúng ta thực hiện đấu nối và thiết đặt IP trên các cổng theo sơ đồ đã chỉ ra.

**Bước 2: Cấu hình dự phòng đường đi với static route**
***Cấu hình:***
Chúng ta sử dụng tham số AD trong câu lệnh cấu hình static route trên các router để thực hiện yêu cầu này.
Trên R1
```console
R1(config)# ip route 192.168.2.0 255.255.255.0 192.168.12.2 5 <- Set AD = 5
R1(config)# ip route 192.168.2.0 255.255.255.0 192.168.21.2 10 <- Set AD = 10
```

Trên R2
```console
R2(config)# ip route 192.168.1.0 255.255.255.0 192.168.12.1 10
R2(config)# ip route 192.168.1.0 255.255.255.0 192.168.21.1 5
```

***Kiểm tra:***
Bảng định tuyến của R1:
```console
R1# show ip route static
S     192.168.2.0/24 [5/0] via 192.168.12.2
```

Hiện tại, R1 đang thực hiện chọn đường đi đến subnet loopback 0 của R2 theo next - hop 192.168.12.2 (đường nối giữa 2 cổng F0/0).
Shutdown cổng F0/0 của R1 để giả lập tình huống đứt đường chính:
```console
R1(config)# interface f0/0
R1(config-if)# shutdown
R1(config-if)#
*Mar  1 00:06:48.623: %LINK-5-CHANGED: Interface FastEthernet0/0, changed
state to administratively down
*Mar  1 00:06:49.623: %LINEPROTO-5-UPDOWN: Line protocol on Interface
FastEthernet0/0, changed state to down
```

Kiểm tra lại bảng định tuyến của R1 để xác nhận rằng lúc này R1 đã tự chuyển sang đi theo đường dự phòng:
```console
R1# show ip route static
S     192.168.2.0/24 [10/0] via 192.168.21.2
```

No shutdown cổng F0/0 của R1 để khôi phục lại đường chính:
```console
R1(config)# interface f0/0
R1(config-if)# no shutdown
R1(config-if)#
*Mar  1 00:09:50.395: %LINK-3-UPDOWN: Interface FastEthernet0/0, changed
state to up
*Mar  1 00:09:51.395: %LINEPROTO-5-UPDOWN: Line protocol on Interface
FastEthernet0/0, changed state to up
```

Kiểm tra bảng định tuyến của R1 để xác nhận rằng R1 đã đi theo đường chính trở lại:
```console
R1# show ip route static
S     192.168.2.0/24 [5/0] via 192.168.12.2
```

Thực hiện kiểm tra tương tự cho router R2 với static route đi đến subnet 192.168.1.0/24 của R1.
**Cấu hình đầy đủ:**
**R1:**
```console
!
interface Loopback0
 ip address 192.168.1.1 255.255.255.0
!
interface FastEthernet0/0
 no shutdown
 ip address 192.168.12.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no shutdown
 ip address 192.168.21.1 255.255.255.0
 duplex auto
 speed auto
!
ip route 192.168.2.0 255.255.255.0 192.168.12.2 5
ip route 192.168.2.0 255.255.255.0 192.168.21.2 10
```

**R2:**
```console
!
interface Loopback0
 ip address 192.168.2.1 255.255.255.0
!
interface FastEthernet0/0
 no shutdown
 ip address 192.168.12.2 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no shutdown
 ip address 192.168.21.2 255.255.255.0
 duplex auto
 speed auto
!
ip route 192.168.1.0 255.255.255.0 192.168.21.1 5
ip route 192.168.1.0 255.255.255.0 192.168.12.1 10
```

**Câu hỏi ôn tập:**
1. Hãy nêu công dụng của giá trị AD - Administrative Distance khi được sử dụng trong định tuyến.
- Xác định đường đi ưu tiên của gói tin.

2. Cho biết mặc định giá trị AD của các static route được cấu hình trên router Cisco là bao nhiêu?
- Giá trị AD Default là 1.