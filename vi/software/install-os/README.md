# INSTALL OS - Cài đặt hệ điều hành
- Hướng dẫn cài đặt hệ điều hành căn bản (dành cho người chưa biết).

## INSTALL WINDOW - Cài đặt hệ điều hành Window
### PREPARE - Chuẩn bị
- Đối với Window thì lên Google search từ khóa "windows installation media" hoặc "windows iso", "windows install", ...
- Lựa chọn version hệ điều hành muốn cài đặt.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media.jpg?raw=true)
- Click vào nút "Download tool now" để tải file hổ trợ download hệ điều hành.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-download.jpg?raw=true)
- Trình duyệt sẽ tải về 1 file exe, sau khi tải xong thì click vào để chạy ứng dụng. Lúc này hệ điều hành vẫn chưa tải về.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-tool-run.jpg?raw=true)
- Khi form "license terms" hiện lên thì click nút "Accept" để đến form lựa chọn. Có thời gian thì nên đọc hết nội dung License.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-tool-accept.jpg?raw=true)
- Chọn "Create installation media" để tạo file ISO và click "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-tool-select-media.jpg?raw=true)
- Nếu muốn tải file ISO cho window 32 bit hoặc file ISO cho cả 2 là 32 bit và 64 bit thì bỏ tick vào "Use the recommended options for this PC". Cuối cùng click "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-tool-select-iso.jpg?raw=true)
- Cuối cùng chọn định dạng là file ISO, nếu muốn tạo trực tiếp cài đặt trên USB thì chọn "USB flash driver" và cắm USB vào. Cuối cùng click "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-tool-final.jpg?raw=true)
- Cuối cùng chọn chổ lưu file ISO hoặc USB cần setup.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/windows-installation-media-finish.jpg?raw=true)
- Bây giờ là chờ đợi thôi.
- Đối với file ISO thì nếu chọn 1 trong 2 version 32 bit hoặc 64 bit thì dung lượng từ 3GB đến 5GB thì mất khoảng hơn 30 phút (tùy tốc độ mạng).
- Đối với file ISO both chứa cả 2 version 32 bit và 64 bit thì dung lượng trên 6GB nên sẽ lâu hơn => nên chọn 1 version thôi cho nhanh.
- Sau khi tải xong file ISO thì có 2 cách để xử dụng.
    1. Trên máy tính windown thì có thể click chuột phải vào file ISO rồi chọn "Mount" để bung file ra thành 1 ổ đĩa ảo. Sau đó copy toàn bộ nội dung ổ đĩa ảo sang USB (Lưu ý nên để USB format FAT32 để dễ nhận dạng windows install).
    2. Ghi ra đĩa DVD để dùng cho máy tính có đầu đọc đĩa (Admin thích nhất cách này).
    3. Sử dụng 1 ứng dụng của bên thứ 3 để setup 1 USB multi install để cài đặt nhiều hệ điều hành. Ví dụ: Yuml, USB Multiboot, ... (Admin không thích lắm vì dễ nhiễm virus từ các ứng dụng này).

### INSTALL - Cài đặt
- Gắn USB hoặc cho DVD vào PC hay Laptop.
- Reset lại PC hay Laptop.
- Tùy theo mainboard và BIOS sẽ có phím khởi động menu boot (F2, F10, F12 hay DEL).
- Lựa chọn boot bằng USB hoặc ổ đĩa quang chứa DVD.
- Màn hình cài đặt hiện lên. Lựa chọn ngôn ngữ và múi giờ để cài đặt (Admin thường chọn ngôn ngữ là English - Mặc định vì dùng quen rồi, Chọn Time và currency format là Vietnam, keyboard thì chọn mặc định là US). Cuối cùng click vào "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-1.jpg?raw=true)
- Kế tiếp sẽ hiện lên màn hình hỏi rằng là cài đặt mới hay sửa chửa window hiện có trên máy tính. Click vào "Install now".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-2.jpg?raw=true)
- Kế đến là màn hình nhập license key (có thì nhập luôn - Admin dùng active by cmd nên chọn "I don't have a product key"). Nếu nhập license key ok thì click "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-3.jpg?raw=true)
- Kế đến là màn hình chọn edition của Windows (Hay còn gọi là phiên bản). Chọn xong click vào "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-4.jpg?raw=true)
- Phổ biến có 4 phiên bản :
    1. Home : Là phiên bản người dùng cá nhân chỉ yêu cầu cơ bản là làm việc văng phòng và giải trí. Coder thì đừng nên chọn vì nó thiếu tính năng Hyper-X, Remote Desktop, ... (Admin không khuyến khích dùng vì nó lỏm lỏm). Đặc biệt Edition N thì bị bỏ bớt thêm 1 số tính năng liên quan đến trình xem video và nghe nhạc. Edition Single Language thì còn thảm hại hơn, không cho thay đổi ngôn ngữ => không thêm được bàn phím (Admin thường dùng bàn phím US, VI - Number, Japan - MEI) nên rất gét edition này nhưng hầu như laptop nào cũng được cài mặc định như vậy.
    2. Education : Là phiên bản người dùng là học sinh được miễn phí theo thời hạn. Tính năng cũng tạm ổn nhưng cũng không nên dùng.
    3. Pro : Là phiên bản người dùng cao cấp. Cài window thì cứ chọn Edition này là tốt nhất nhưng đồng thời giá LICENSE sẽ mắc hơn Edition Home.
    4. Enterprise : Là phiên bản người dùng dành cho doanh nghiệp. Trong file ISO không có đâu vì nó sẽ được bán riêng biệt cho doanh nghiệp.
- Kế đến là màn hình thông báo LICENSE. Có thời gian thì cứ đọc cho biết (Admin có không đọc đâu nhé vì không quan tâm lắm).
Xong thì click vào ô "I accept the license terms" thì button "Next" sẽ click được.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-5.jpg?raw=true)
- Lại quay lại màn hình lựa chọn "Update" hay "Install" window (Admin thấy nó có vẻ khác là thừa thải vì nên để ở màn hình đầu tiên luôn). Click vào vùng có dòng chữ "Custom: Install Windows only" để bắt đầu cài đặt window.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-6.jpg?raw=true)
- Chọn ổ cứng để dùng cài đặt window. Ừ thì nếu là ổ cứng mới thì cứ việc chọn thôi, thường Admin sẽ chọn ổ Driver 0 hoặc ổ có dung lượng chừng 120GB đến 500GB vì đó thường là ổ SSD, còn không có ổ SSD thì có thể chọn ổ HDD. Thích thì cứ việc phân vùng luôn lúc này nhưng nếu là ổ HDD thì nên phân vùng luôn vì nếu phân vùng luôn thì nó sẽ cài nhanh hơn do nó sẽ không chạy hết cả ổ HDD để format mà chỉ format 1 vùng nhỏ chừng 120GB - 240GB (Admin thích để nó nhỏ nhỏ như vậy). Phân vùng thì cứ click vào "Extend" để phân vùng. Window sẽ có 2-4 phân vùng cơ bản (Đối với BIOS cũ theo chuẩn MBR hay Legacy thì sẽ có 2 phân vùng là Boot và Data, Còn BIOS mới thì theo chuẩn UEFI hay GDT thì có 3-4 phân vùng là Boot, Repair, Backup, Data). Chuẩn GDT sẽ có thể tạo hơn 4 phân vùng cho đến 128 phân vùng trên 1 ổ cứng nhưng cũng chả ai rãnh tạo nhiều phân vùng trên 1 ổ cứng ngoại trừ ổ cứng boot hệ điều hành.
- Nếu không phân vùng thì chương trình sẽ tự phân vùng cho mình luôn (Admin chọn cách này).
- Click vào button "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-7.jpg?raw=true)
- Cuối cùng là ngồi chờ 10-15 phút cho SSD và 30 phút đến 1 tiếng tùy HDD.
- Khi xong thì sẽ tự reset.
- Chưa xong đâu, đừng mừng vội. Bây giờ là phần config cho user. Haiz, chả hiểu chọn 1 đống lúc setup rồi giờ phải chọn lại.
- Chọn vùng miền (Admin chọn Vietnamese nhưng nếu lười thì để default luôn).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-8.jpg?raw=true)
- Chọn keyboard (Admin thì chọn US, xong rồi thì vào cài thêm sau).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-9.jpg?raw=true)
- Window sẽ ráng hỏi lại lần nữa có muốn thêm Keyboard hay không. Chọn "Skip" Để tiếp tục.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-10.jpg?raw=true)
- Chọn loại tài khoản => chỉ nên chọn loại "Set up for personal user". Click "Next".
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-11.jpg?raw=true)
- Window sẽ hỏi là có muốn login tài khoản online hay không (Admin sẽ chọn Offline Account rồi, Activate by cmd mà).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-12.jpg?raw=true)
- Ờ thì tới màn hình gì đó thì chọn "Limited experience" thoai. Đừng click "Get it now" nhé.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-13.jpg?raw=true)
- Nhập username offline thôi.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-14.jpg?raw=true)
- Nhập password offline thôi. Không nhập cũng được (Admin lười nên không nhập luôn).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-15.jpg?raw=true)
- Nếu nhập password thì sẽ chọn 3 câu hỏi với 3 câu trả lời để khôi phục mật khẩu window nếu quên (Lý do admin không nhập mật khẩu).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-16.jpg?raw=true)
- Ờ thì tới màn hình gì đó mình chọn "No" thoai, không là nó bắt quay lại trang login bằng online (phiền ghê).
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-17.jpg?raw=true)
- Màn hình chọn setting. Admin off hết cho nhẹ máy và không chiếm băng thông. Laptop thì có thể on hết. Click "Accept" thoai.
![Select page](https://github.com/phucnh1993/training/blob/master/vi/software/install-os/image/install-win-10-step-18.jpg?raw=true)
- Thế là quá trình cài đặt đã kết thúc và chờ nó chạy 1 chút là vào được window roài. Chúc cả nhà thành công!

### ACTIVATE - Kích hoạt
- Ờ thì có 3 cách kích hoạt chính :
    1. Nhập license key : easy, tốn tiền mua thoai. Mà có 2 loại license key nha. Loại nhập 1 lần và chạy trên 1 máy (Theo giá hiện tại là 3 củ). Loại nhập n lần và chạy trên 1 máy tại 1 thời điểm (Có thể activate trên nhiều máy - nhưng lúc activate thì tắt các máy kia đi không là bị block key).
    2. App activate key : easy, dễ nhiễm virus, 6 tháng chạy 1 lần, Admin không khuyên dùng. Dùng thì thà khỏi activate luôn cho lành.
    3. Activate by cmd : cũng không khó lắm. Search activate by cmd trên mạng, rồi mở cmd bằng quyền Administrator lên và làm theo. Ít nhiễm virus hơn và không phải activate lại. Thực chất thì mấy cái app activated cũng chạy tre6b nguyên tắc này nhưng thêm 1 số dòng lệnh cài virus và làm màu.

## INSTALL LINUX - Cài đặt hệ điều hành Linux
### PREPARE - Chuẩn bị
- Do linux có rất nhiều hệ điều hành nên Admin không viết rỏ được, chỉ nêu chung chung thoai.
- Có 3 loại hệ điều hành Linux chính là : Desktop và Server và mini container.
- Chúng khác nhau là Server sẽ nhẹ hơn Desktop cho cắt bỏ bớt phần giao diện, mini container là nhẹ nhất nhưng câu lệnh nó sẽ khác nhất do nó được viết riêng biệt, chưa có app hổ trợ.
Vì Server thì cần gì giao diện để nhìn.
- Các hệ điều hành Linux phổ biến mà Admin từng dùng : Ubuntu (ừ thì thằng này đầy đủ tool, nhưng Admin không có quyền root nên ít xài, do gõ lệnh phải gõ thêm sudo, phiền quá với file iso và cài đặt rất nặng), Debian (nhẹ, có giao diện và không cần sudo), Centos (từ khi lên version 8 thì hết xài do nó yêu cầu update liên tục), ...
- Lên trang chủ của hệ điều hành và tải file iso của nó về sau đó làm giống windown là "Mount" ra rồi copy vào USB hoặc ghi ra DVD.

### INSTALL - Cài đặt
- Do mỗi hệ thống Linux sẽ có giao diện khác nhau hoặc thậm chí không có giao diện nên ờ thì bỏ qua phần hướng dẫn chi tiết như window nhé. Cần thì tìm hướng dẫn chi tiết từng loại trên mạng nhé. (Chủ yếu do Admin lười thôi)
- Tóm lại cài đặt của hệ điều hành Linux cũng theo các bước sau :
    1. Chọn ngôn ngữ và vùng miền.
    2. Chọn server để tải update (Chọn server gần vietnam để update cho nhanh).
    3. Phân vùng ổ cứng (Admin thường phân 3 vùng chủ yếu: SWAP *Ram ảo*, Boot *Load hệ điều hành*, Root */ nơi chứa source*)
    4. Chọn ứng dụng cài thêm và loại giao diện (nên chọn cài thêm SSH).
    5. Cài đặt user Root và 1 user sử dụng hằng ngày.
    6. Cấu hình linh tinh theo ứng dụng chọn cài đặt thêm.
    7. Ngồi chờ cài đặt (Nếu file iso là phiên bản đầy đủ sẽ cài nhanh hơn file iso là bản cài qua net).
- Sau khi cài đặt xong thì nếu có cài đặt giao diện thì sẽ nhìn thấy giao diện như window.
- Nếu cài đặt không xài giao diện thì sẽ chỉ hiển thị màn hình command line.
- Tuy nhiên đa số hệ điều hành linux có hổ trợ cài đặt thêm giao diện và chuyển qua chuyển lại xài command line hoặc giao diện.
- Vì vậy để tiết kiệm thời gian cài đặt thì nên cài không giao diện rồi update switch qua giao diện nếu cần thiết.

### ACTIVATE - Kích hoạt
- Hệ điều hành Linux thường Free ngoại trừ 1 số như : Red Hat hay một số dạng Enterprise.
- Admin xài Linux free nên không biết activate như thế nào cả.

## INSTALL MACOS - Cài đặt hệ điều hành MacOS
- Admin skip qua cái này nhé, chừng nào có tiền mua Mac thì admin sẽ làm hướng dẫn.
- Goodbye, see you again!