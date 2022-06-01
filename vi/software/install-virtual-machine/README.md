# INSTALL VIRTUAL MACHINE - Cài đặt máy ảo
- Máy ảo là một thành phần quan trọng trong hệ thống. Thường dùng cho mục đích test, kiểm tra phần mềm hay giả lập các môi trường hệ thống.
- Có 2 loại máy ảo và ảo hóa :
    1. Máy ảo trên nền một máy thật. Máy ảo sẽ được máy thật quản lý.
    2. Ảo hóa toàn bộ một máy tính hay server. Có nghĩa là không cần một máy ảo quản lý mà là dùng một hệ thống ảo quản lý toàn bộ máy ảo. Hay áp dụng trên server.
- Lưu ý khi sửu dụng máy ảo là phân phối tài nguyên hợp lý vì khi một máy ảo muốn thay đổi tài nguyên thì phải tắt đi mở lại có thể gây ảnh hưởng hệ thống.
- Máy ảo sẽ chậm hơn máy thật nhưng sẽ dễ backup và restore hơn máy thật.

## PREPARE - Chuẩn bị
- Tải file ISO của hệ điều hành muốn cài.
- Bật tính năng ảo hóa trên BIOS là Virtualization Technology trong System Security.

## HYPER-V - Máy ảo Hyper-V
- Máy ảo Hyper-V là máy ảo của riêng hệ điều hành Window.
- Do tích hợp cùng Window nên có lợi thế hơn các loại máy ảo khác do share tài nguyên dễ hơn, có thể setup khởi động cùng hệ thống và chạy tốn ít tài nguyên hơn.
- Phù hợp cho sử dụng ảo hóa cho máy ảo là Window, Window Server. Đối với Linux thì nên xài dạng Command Line còn xài giao diện sẽ lag hơn.
- Dễ cài đặt nhưng hay lỗi vặt.
- Thích hợp dùng cho Docker.
- Hổ trợ khởi động chạy ngầm cùng hệ thống.
- Thích hợp cho máy cấu hình yếu.

### INSTALL HYPER-V - Cài đặt Hyper-V
- Vào "Control Panel" để install máy ảo trong "Programs and Features".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/control-panel.jpg?raw=true)
- Chọn "Turn Windows features on or off".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/programs-and-features.jpg?raw=true)
- Click chọn Hype-V để cài đặt vào hệ thống sau đó thì restart máy tính.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/install-hyper-v.jpg?raw=true)
- Sau khi cài xong thì nhấn vào Start menu => Search từ khóa Hyper-V.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-manager.jpg?raw=true)
- Nếu xuất hiện thì cài Hyper-V thành công.

### USE HYPER-V - Sử dụng Hyper-V
- Sau khi mở ứng dụng Hyper-V manager lên.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-switch.jpg?raw=true)
- Tạo switch cho máy ảo, gồm 3 loại switch :
    1. External : Được sử dụng nhiều nhất. Là tùy chọn mà có thể được map vào card mạng vật lý (xài chung với switch thật). Khi tạo External, card mạng sẽ không thể đặt IP được nữa, bạn phải đặt IP ở Connection mới tạo là vEthernet (External Network).
    2. Internal : Các máy ảo có thể liên lạc được với máy thật (máy Host). Khi chọn Internal, bạn kiểm tra trên máy Host sẽ thấy có thêm card mạng mới là vEthernet (Internal Network). Dạng này có thể áp dụng trên thực tế.
    3. Private : Không dùng trên thực tế được, áp dụng trong môi trường lab (thực hành), cô lập mạng máy ảo với hệ thống mạng bên ngoài.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-switch-select.jpg?raw=true)
- Tạo máy ảo trên Hyper-V : Click Host -> New -> Virtual Machine.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-1.jpg?raw=true)
- Màn hình giới thiệu về máy ảo -> Click "Next" để bỏ qua.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-2.jpg?raw=true)
- Đặt tên máy ảo và chọn nơi lưu trữ thông tin máy ảo, ổ cứng ảo, cấu hình ảo.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-3.jpg?raw=true)
- Chọn thế hệ máy ảo (Admin cứ chọn "Generation 1" cho lành).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-4.jpg?raw=true)
- Nhập số lượng RAM ảo tối đa mà hệ thống cung cấp cho máy ảo. Nếu dùng Dynamic Memory thì RAM ảo sẽ được hệ thống tự điều chỉnh cho phù hợp, không chọn thì hệ thống sẽ fix cứng dung lượng RAM ảo -> dung lượng RAM thật sẽ bị hụt đi nhiều.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-5.jpg?raw=true)
- Chọn switch cho máy ảo. Thường chọn switch là External hoặc Internal thôi, Private rất ít dùng.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-6.jpg?raw=true)
- Chọn dung lượng ổ cứng ảo và nơi lưu trữ, Admin thường setup luôn 500GB để khỏi lăn tăn về việc tăng dung lượng sau này.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-7.jpg?raw=true)
- Chọn file ISO chứa source của hệ điều hành.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-8.jpg?raw=true)
- Xác nhận thông tin máy ảo.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-9.jpg?raw=true)
- Click "Finish" và chờ hệ thống cài đặt và tạo máy ảo.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-10.jpg?raw=true)
- Giờ ra màn hình manager và start máy ảo lên
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-virtual-machine/image/hyper-v-create-machine-11.jpg?raw=true)
- Sau khi start máy ảo lên thì sẽ hiện màn hình setup hệ điều hành nếu máy ảo chưa có hệ điều hành.

## VIRTUAL BOX - Máy ảo Virtual Box
- Máy ảo Virtual Box là phần mềm điều khiển máy ảo miễn phí.
- Tương đối ổ định nhưng hiệu năng chỉ tương đương Hype-X.
- Hổ trợ backup, clone máy ảo tốt hơn Hyper-V. Nhưng bị giới hạn số lượng clone.
- Cũng có hệ thống card mạng tương đối.
- Đồ họa thì giật lag hơn Hype-X.
- Không hổ trợ khởi động chạy ngầm cùng hệ thống.
- Thích hợp cho máy cấu hình yếu.

### INSTALL VIRTUAL BOX - Cài đặt Virtual Box

### USE VIRTUAL BOX - Sử dụng Virtual Box

## VMWARE PRO - Máy ảo VmWare
- Máy ảo VmWare là phần mềm điều khiển máy ảo có trả phí.
- Tối ưu hệ thống sử dụng card đồ họa nên chỉ cần cài driver VmWare vào sẽ không bị giật lag.
- Quản lý hệ thống card mạng tốt.
- Hệ thống quản lý CPU, RAM, VGA mạnh mẽ. Có thể chơi game được trên máy ảo.
- Không hổ trợ khởi động chạy ngầm cùng hệ thống.

### INSTALL VMWARE - Cài đặt VmWare

### USE VMWARE - Sử dụng VmWare