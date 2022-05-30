# INSTALL VIRTUAL MACHINE - Cài đặt máy ảo
- Máy ảo là một thành phần quan trọng trong hệ thống. Thường dùng cho mục đích test, kiểm tra phần mềm hay giả lập các môi trường hệ thống.
- Có 2 loại máy ảo và ảo hóa :
    1. Máy ảo trên nền một máy thật. Máy ảo sẽ được máy thật quản lý.
    2. Ảo hóa toàn bộ một máy tính hay server. Có nghĩa là không cần một máy ảo quản lý mà là dùng một hệ thống ảo quản lý toàn bộ máy ảo. Hay áp dụng trên server.
- Lưu ý khi sửu dụng máy ảo là phân phối tài nguyên hợp lý vì khi một máy ảo muốn thay đổi tài nguyên thì phải tắt đi mở lại có thể gây ảnh hưởng hệ thống.
- Máy ảo sẽ chậm hơn máy thật nhưng sẽ dễ backup và restore hơn máy thật.

## INSTALL HYPER-X - Cài đặt máy ảo Hyper-X
- Máy ảo Hyper-X là máy ảo của riêng hệ điều hành Window.
- Do tích hợp cùng Window nên có lợi thế hơn các loại máy ảo khác do share tài nguyên dễ hơn, có thể setup khởi động cùng hệ thống và chạy tốn ít tài nguyên hơn.
- Phù hợp cho sử dụng ảo hóa cho máy ảo là Window, Window Server. Đối với Linux thì nên xài dạng Command Line còn xài giao diện sẽ lag hơn.
- Dễ cài đặt nhưng hay lỗi vặt.
- Thích hợp dùng cho Docker.
- Hổ trợ khởi động chạy ngầm cùng hệ thống.
- Thích hợp cho máy cấu hình yếu.

### PREPARE - Chuẩn bị
- Tải file ISO của hệ điều hành muốn cài.
- Vào "Control Panel" để install máy ảo trong "Programs and Features".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/control-panel.jpg?raw=true)
- Chọn "Turn Windows features on or off".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/programs-and-features.jpg?raw=true)
- Click chọn Hype-V để cài đặt vào hệ thống sau đó thì restart máy tính.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/install-hyper-v.jpg?raw=true)

## INSTALL VIRTUAL BOX - Cài đặt máy ảo Virtual Box
- Máy ảo Virtual Box là phần mềm điều khiển máy ảo miễn phí.
- Tương đối ổ định nhưng hiệu năng chỉ tương đương Hype-X.
- Hổ trợ backup, clone máy ảo tốt hơn Hyper-X. Nhưng bị giới hạn số lượng clone.
- Cũng có hệ thống card mạng tương đối.
- Đồ họa thì giật lag hơn Hype-X.
- Không hổ trợ khởi động chạy ngầm cùng hệ thống.
- Thích hợp cho máy cấu hình yếu.

## INSTALL VMWARE PRO - Cài đặt máy ảo VmWare
- Máy ảo VmWare là phần mềm điều khiển máy ảo có trả phí.
- Tối ưu hệ thống sử dụng card đồ họa nên chỉ cần cài driver VmWare vào sẽ không bị giật lag.
- Quản lý hệ thống card mạng tốt.
- Hệ thống quản lý CPU, RAM, VGA mạnh mẽ. Có thể chơi game được trên máy ảo.
- Không hổ trợ khởi động chạy ngầm cùng hệ thống.