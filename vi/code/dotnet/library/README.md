# LIBRARY - Thư viện trong .NET
- Để xử dụng thư viện trong .NET thì chúng ta sẽ pull về từ Nuget hoặc 1 server từ vên thứ 3.
- Để khai báo 1 thư viện để sử dụng thì ta thêm thông tin về gói thư viện đó trong file csproj.
- Ví dụ:
```XML
  <ItemGroup>
    <PackageReference Include="Dapper" Version="2.0.123" />
    <PackageReference Include="System.ComponentModel.Annotations" Version="5.0.0" />
    <PackageReference Include="System.Data.SqlClient" Version="4.8.3" />
  </ItemGroup>
```
- Thông tin khai báo bao gồm 1 thẻ XML với tên thẻ là **PackageReference** và 2 attribute là **Include** - Tên của library và **Version** - Số phiên bản sử dụng.
- Sau khi khai báo trong  file csproj thì chúng ta sẽ chạy lệnh restore để .NET biết và pull thư viện cần dùng về.
- Sau khi pull về thì ta mới sử dụng được lệnh Using trong file cs (Lúc này các trình gõ code mới biết nội dung của thư viện đó gồm có các namespace, class, inteface, function gì).
- Những thư viện này thường được viết dưới tổ hợp nhiều version của ngôn ngữ lập trình .NET nhưng phổ biến nhất là chúng phải hổ trợ các version sau: Net Framework 4.5, Net standard 1.0, Net standard 2.0, Net standard 2.1, Net Core 3.1, Net 5.0, Net 6.0, ...
- Thư viện là những đoạn code xử lý 1 loại đối tượng được lập trình từ coder nhằm mục đích tái xử dụng những đoạn code lập đi lập lại hoặc dùng để che dấu mã nguồn (vì thư viện đã được đóng gói thành những file dll).
- Phải lưu ý khi sử dụng thư viện là nó phải hổ trợ cho version .NET là bao nhiêu và license của thư viện vì một số thư viện là free nhưng một số khác sẽ tính phí khi sử dụng hoặc phải gọi API của thư viện (những thư viện gọi API có thể lấy data của người sử dụng - cẩn thận liên quan đến security).