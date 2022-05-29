# HARDWARE - Phần cứng máy tính
- Phần cứng (Hardware) là những thiết bị bên trong và bên ngoài máy tính mà chúng ta có thể cầm được, nhìn thấy được.
Phần cứng máy tính chính là các bộ phận tạo thành một chiếc máy tính.
Các bộ phận đó bao gồm :
    1. Phần bên ngoài : Màn hình máy tính, tai nghe headphone, bàn phím keyboard, chuột máy tính mouse, máy in, máy chiếu, loa, USB, ...
    2. Phần bên trong : bộ nguồn, chip CPU, bo mạch chủ mainboard, Modem, quạt tản nhiệt, RAM, ROM, card âm thanh, card màn hình, một số Drive như: Bluray, CD-ROM, DVD, ổ cứng, ổ đĩa mềm, ...
- Phần cứng được sản xuất bởi các công ty máy tính như là: Dell, Asus, Lenovo, ...

## CPU - Central Processing Unit
- Là một tấm mạch nhỏ, bên trong có chứa một miếng wafer silicon bao bọc trong một con chíp làm bằng gốm và được gắn vào bảng mạch (mainboard).
- Tốc độ của CPU được đo với đơn vị Hertz (Hz) hoặc Gigahertz (GHz).
- Giá trị đo này càng lớn thì CPU hoạt động càng nhanh.
- CPU có 3 loại :
    1. Loại dùng cho PC, Server : Sức mạnh được đo bằng số nhân (Core) và số luồng (Thread).
    Dễ thay thế nhưng phải cùng socket.
    2. Loại dùng cho thiết bị di động, Laptop : Tương tự như loại cho PC và Server nhưng nhỏ hơn, yếu hơn do tiết kiệm điện và bị hàn dính vào mainboard.
    3. Loại dùng cho CARD màn hình : Có số lượng nhân rất lớn nhưng tốc độ xử lý không cao.

## Mainboard - Bo mạch chủ
- Là bảng mạch chính, là phần quan trọng nhất trong hệ thống máy tính.
- Nó có vai trò trung gian kết nối, giao tiếp giữa các thiết bị khác trong máy tính.
- Việc kết nối và điều khiển bình thường là được thực hiện bởi các chip cầu Nam và cầu Bắc.
- Tuy nhiên hiện tại chip cầu bắc đã được tích hợp vào CPU đề tăng tốc độ của PC. 
- Đấy chính là trung tâm điều chỉnh các hoạt động của máy tính.
- Đối với mainboard cho CPU core I7 đời 2 và 3 thì mainboard có kênh nhớ 3 nên mainboard trang bị 6 khe cắm RAM.
- Mainboard của PC có các loại sau:
    1. A-2, H-1 : Dòng mainboard tối giản, phù hợp CPU loại tiết kiệm điện hoặc nhu cầu văn phòng.
    Có 2 khe cắm RAM.
    Có 1 khe PCIe.
    2. B-5, B-6 : Dòng mainboard đủ tính năng, phù hợp CPU nhiều hơn 2 Core và dưới 10 Core hoặc có nhu cầu chơi game.
    Có 2-4 khe cắm RAM.
    Có 2-3 khe PCIe.
    3. H-7 : Dòng mainboard cao cấp, phù hợp cho nhu cầu máy tính hoạt động liên tục của intel.
    Có 4 khe cắm RAM.
    Có 2-4 khe PCIe.
    4. X-7, Z-9 : Dòng mainboard cao cấp nhất, phù hợp cho nhu cầu ép xung và sở hữu nhiều nhiều cổng PCIe.
    Có 4-8 khe cắm RAM.
    Có 3-8 khe PCIe.
    5. Main Server : Dòng mainboard dùng cho server, dùng cho hệ thống muốn có từ 2 CPU trở lên và dùng RAM với 4 kênh bộ nhớ và có ECC.
    Có 8-24 khe cắm RAM.
    Có 4-10 khe PCIe.

## RAM - Random Access Memory
- Là thiết bị cho phép lưu trữ dữ liệu trong một khoảng thời gian ngắn.
Bộ nhớ của PC là nơi lưu giữ thông tin để các phần mềm được cài đặt trên máy tính truy cập vào lấy dữ liệu.
- RAM là nơi mà máy tính truy cập vào nhằm xử lý thông tin 1 cách tạm thời.
Có nghĩa là khi máy tính không hoạt động thì RAM sẽ trống không.
Còn khi RAM càng lớn thì lưu lượng công việc mà nó giải quyết được càng nhiều.
- Có 4 loại RAM thường xuất hiện trên thị trường :
    1. RAM cho PC, Máy tính bàn : Là 1 mạch gồm 8 chip nhớ cho định dạng DDR4 trở về trước và 20 chip nhớ cho định dạng DDR5.
    RAM-DDR5 có 20 chip nhớ vì nó sử dụng dạng bộ nhớ dạng chia thành 4 kênh (gấp đôi số kênh ở bộ nhớ cũ) và trang bị thêm tính năng ECC nên yêu cầu 1 cặp chip.
    Đồng thời RAM-DDR5 di chuyển chip control bộ nhớ từ mainboard lên mạch RAM nhằm tăng tốc độ và giảm điện năng tiêu thụ (Gần chip nhớ hơn thì tốn ít điện hơn và nhanh hơn).
    RAM cho PC không tương thích với Laptop, Server.
    2. RAM cho Laptop : Là 1 mạch gồm 8 chip nhớ cho định dạng DDR4 và với DDR5 thì chưa có thông tin.
    RAM dùng cho Laptop sẽ ngắn hơn và chip nhớ được sắp xếp theo dạng song song giống như RAM-DDR5 của PC.
    RAM cho Laptop không tương thích với PC, Server.
    3. RAM cho Server : Là 1 mạch gồm 9 chip nhớ (Ít xài nên không có nhiều thông tin).
    RAM có tín năng ECC nên sẽ có 1 chip nhớ dư để làm chip nhớ sửa lỗi.
    RAM cho Server không tương thích với PC, Laptop.
    4. RAM cho thiết bị : Là 1 chip nhớ có dung lượng tùy vào cấu hình.
    RAM cho thiết bị được hàn dính trên thiết bị (có thể thay thế, nhưng phải cùng loại và phải có hàn để tháo ra).
    RAM được gắn trực tiếp trên thiết bị nên giá thành rẻ hơn, tốc độ cao hơn.
    Các loại thiết bị gắn RAM là CARD-PC (Card màn hình, Card mạng), Thiết bị di động (Mobile, Router, Moderm, Switch), ...
- RAM sẽ luôn có 1 con chip đùng để control.
Chip control sẽ là dạng flash chip.
Chip nhớ có thể thay thế nhưng phải lưu ý là cùng dung lượng và cùng hãn sản xuất, lý do là nếu không cùng dung lượng và cùng hãn sản xuất thì chip control sẽ không nhận dạng được.

## SSD - Solid State Drive
- Là bộ lưu trữ chính của mấy tính.
- Là một bản mạch chỉ gồm chip control và chip nhớ.
- Chip nhớ là loại ghi được nhiều lần nhưng có giới hạn ghi, khi tới giới hạn chip nhớ sẽ không ghi được nữa.
- Do SSD không có phần trục quay như HDD nên sẽ tiết kiệm điện hơn và nhỏ gọn hơn.
- SSD thì có 2 dạng chính :
    1. Size 2.5 Inch : Có thể làm ổ gắn trong và gắn ngoài, do tiết kiệm điện nên không cần nguồn phụ.
    Dùng dạng kết nối SATA3 hoặc USB.
    2. Dạng card : là một bản mạch sẽ gắn vào máy tính qua cổng NVMe hoặc PCIe.
- Tốc độ đọc ghi cao, thấp nhất là 500MB/s.
- Giá đắt gấp 4 lần HDD.
- Mát hơn, im lặng hơn HDD do không có trục quay và tiết kiệm điện.
- Thường dùng chứa hệ điều hành để khởi động nhanh.

## HDD - Hard Disk Drive
- Là bộ lưu trữ chính của máy tính, là thiết bị chứa đựng những tấm đĩa hình tròn bao phủ lớp từ tính có tác dụng lưu trữ dữ liệu.
- Ổ cứng là nới lưu trữ hệ điều hành của máy, tất cả phần mềm và mọi dữ liệu.
Khi nguồn bị tắt, tất cả những gì bạn vừa làm việc trên máy tính đều sẽ được giữ lại trên ổ cứng mà không lo bị mất hay bị xóa khi khởi động lại.
- Dung lượng ổ cứng được tính bằng Gigabyte (GB).
Mỗi ổ cứng thông thường có thể chứa được 500 GB hay thậm chí có thể lên đến hàng ngàn GB ~ hàng TB.
- Hoạt động của HDD không quá phức tạp, đơn giản chỉ dựa trên cơ chế chuyển động quay của đĩa từ và đầu đọc. Đĩa tròn làm từ nhôm, thủy tinh hoặc gốm phủ vật liệu từ tính sẽ chuyển động quanh một động cơ quay, kết hợp với những bo mạch chủ điều khiển để đọc/ghi dữ liệu, giải mã thông tin... Các thao tác của bạn trên máy tính nhanh hay chậm sẽ phụ thuộc vào bộ phận này.
- Dung lượng ghi trên ổ cứng có thể khác số hiển thị trên màn hình máy tính khi hiển thị vì khi sản xuất, nhà sản xuất phủ lớp từ tính theo từng track (rãnh chứa lớp từ tính) theo hệ số thập phân trong khi phần mềm mấy tính lại theo hệ nhị phân làm chênh lệch số bit nhận được.
- Lưu ý là HDD tốc độ truy cập thấp (100MB/s), nóng do đĩa quay, sẽ hư hỏng nếu ổ cứng đang quay và bị di chuyển.
- Cấu tạo HDD gồm 5 thành phần chính :
    1. Phần đầu đọc : Gồm đầu đọc để đọc/ ghi dữ liệu và cần di chuyển đầu đọc này.
    2. Phần đĩa : Gồm trục quay giúp truyền chuyển động từ đĩa và một động cơ quay gắn với trục và đĩa.
    3. Phần mạch điện : Gồm đầu kết nối, đầu cắm nguồn, mạch điều khiển làm nhiệm vụ điều khiển động cơ đồng trục và cần di chuyển, mạch xử lý dữ liệu để xử lý dữ liệu đọc/ghi, bộ nhớ đệm lưu trữ tạm thời dữ liệu , cầu đấu thiết đặt để thiết đặt chế độ làm việc của ổ cứng.
    4. Vỏ đĩa cứng : Gồm phần đế và phần nắp đậy các linh kiện.
    5. Đĩa từ: Được sắp xếp thành cấu trúc cụ thể để duy trì việc truy xuất dữ liệu, cấu trúc đó gồm Track, Sector và Cluster.
- Có 2 loại HDD là :
    1. HDD-Internal : Là ổ cứng gắn trong.
    Có nhiều kích thước.
    Size 2.5 Inch dùng cho Laptop.
    Size 3.5 Inch dùng cho PC.
    Size 5.25 Inch dùng cho PC đời đầu.
    2. HDD-External : Là ổ cứng gắn ngoài.
    Thường truyền dữ liệu qua cổng USB nhưng thường yêu cầu thêm nguồn cấm phụ.
    Có kích thước 2.5 Inch để dễ cho việc di chuyển.
- Tốc độ vòng quay (RPM = Vòng/Phút):
    1. 5400 rpm : thường dùng cho ổ cứng Laptop hoặc ổ cứng tiết kiệm năng lượng.
    2. 7200 rpm : thường dùng cho ổ cứng PC hoặc ổ cứng Server.
    3. >10000 rpm : thường dùng cho PC hoặc Server với yêu cầu đọc và ghi tốc độ cao với dung lượng lớn.
- Các thông số trên HDD :
    1. Disk Capacity HDD: Dung lượng ổ cứng HDD, tính theo đơn vị: byte, Kb, MB, GB, TB.
    2. Average Seek Time HDD: Thời gian tìm kiếm trung bình của ổ cứng, khi đầu đọc di chuyển từ một Cylinder này đến một Cylinder ngẫu nhiên khác.
    3. Random Access Time HDD: Đây là thời gian truy cập ngẫu nhiên của ổ cứng HDD để tìm kiếm một dữ liệu ngẫu nhiên.
    Thông số này rất quan trọng, ảnh hưởng đến hiệu năng của ổ cứng và hệ thống.
    4. Data access time HDD: Là thời gian truy cập dữ liệu của ổ cứng, bằng tổng của Average Seek time và Random Access Time.
    5. MTBF HDD (Mean Time Between Failures HDD): Đây là thời gian làm việc tin cậy ổ cứng HDD, hiểu đơn giản là tuổi thọ của ổ cứng (đơn vị tính bằng giờ).
    Với ổ cứng hoạt động ở tốc độ 15.000 rpm có MTBF lên đến 1,4 triệu giờ.

## IO - Thiết bị đầu vào
- Đây là những thiết bị giúp cung cấp dữ liệu và tập lệnh cho máy tính như là: chuột, touchpad, trackball, bàn phím, bảng vẽ,…

## OUTPUT - Thiết bị đầu ra
- Là thiết bị điện tử không thể thiếu. Chúng có tác dụng chính là hiển thị và kết nối sự giao tiếp giữa người dùng và chiếc máy tính.
- Hiện nay, có rất nhiều loại màn hình được tích hợp cảm ứng do vậy, bạn có thể sử dụng ngón tay chạm lên màn hình để thao tác cũng như điều khiển máy tính.

## CARD - Thiết bị hổ trợ
- Thiết bị ngoại vi được gắn vào máy tính thông qua những khe cắm có băng thông cao.

### CARD mạng
- Để có thể kết nối với Internet thì chắc chắn bạn sẽ phải cần đến card mạng.
Đa phần, máy tính hiện nay đều được tích hợp sẵn ít nhất một chiếc card mạng LAN (không dây hay có dây) trên Mainboard – bo mạch chủ để bạn có thể liên kết tới bộ định tuyến Internet của các nhà mạng.
- Khi card mạng gặp sự cố hỏng hóc, bạn có thể gắn thêm card mạng dời vào khe mở rộng ở bên trong máy tính (PCI hoặc PCI Express 1x) hay loại card dời kết nối qua cổng USB.
- CARD mạng có 2 loại:
    1. Loại có dây : Tùy theo giá thành sẽ có 1-8 cổng mạng (port). Loại có nhiều cổng mạng có thể gắn trên cả router và server.
    2. Loại không dây : Tùy theo giá thành sẽ không có râu hoặc có từ 1-4 râu.

### CARD màn hình
- Dùng để cho PC, Server hoặc Laptop (Có cổng thunderbolt) có thể xuất hình ảnh chất lượng cao.
- Thường dùng cho chơi game, đào tiền ảo , đồ họa, trí tuệ nhân tạo, ...
- Do đặc tính nhiều nhân trong CPU nên chức năng chính là Render hình ảnh.
- Có bộ nhớ riêng. Được trang bị như một máy tính cá nhân nên giá của 1 chiếc card có thể tương đương một chiếc PC.
- CARD màn hình có 2 loại:
    1. CARD chơi game : Giá rẻ, thuật toán tối ưu cho dựng hình nhanh, tiết kiệm năng lượng.
    2. CARD đồ họa : Giá cao, thuật toán tối ưu cho dựng hình đẹp, chạy những bài toán đặc biệt.