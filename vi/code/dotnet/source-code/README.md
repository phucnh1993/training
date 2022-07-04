# SOURCE CODE
- Kiến trúc của source code dotnet :
    1. File <Project_Name>.csproj : là nơi khai báo thông tin loại project (console, winform, webapp or library), những thư viện sử dụng trong project, những import library và những lệnh chạy kèm khi build project.
    2. File Program.cs : là nơi mà khi lệnh dotnet build và dotnet run chạy thì sẽ được đọc đầu tiên trong chương trình, là file quan trọng, không có thì chương trình không chạy.
    3. Thư mục Properties : nơi chứa những file cấu hình căn bản của 1 project (với winform sẽ format theo định dạng xml còn với webapp sẽ định dạng theo json). Gồm các file như sau:
        1. File launchSetting.json : chứa thông tin cấu hình IIS hoặc Console app chạy cho webapp (có cả biến môi trường).
        2. File Settings.property : chứa thông tin cấu hình cho winform.
    4. Tập hợp các file appSetting.{env}.json : là những file chứa thông tin cấu hình cho từng môi trường build app sẽ được chỉ định trong lệnh build của gitlab runner hay một backround service nhận nhiệm vụ build app với env là tên môi trường.
        - Ví dụ : appSetting.json, appSetting.Development.json, appSetting.Test.json, appSetting.Staging.json, appSetting.Production.json.
    5. File Dockerfile : là nơi chứa lệnh để hướng dẫn cho các runner deploy chương trình lên docker của server.
    6. File Startup.cs : là nơi chứa những configuration (cấu hình) của webapp (khi lên dotnet 6.0 thì sẽ không còn thấy do được tích hợp vào trong file Program.cs).
    7. Thư mục Controllers : là nơi khai báo những class chứa thông tin của các API (đường dẫn, biến truyền vào, phương thức [GET, POST, PUT, DELETE]).
    8. Thư mục Views : là nơi chứa các file có đuôi là .cshtml hoặc chứa những đoạn code lập trình giao diện cho Web Page.
    9. Thư mục Models : là nơi chứa các class làm nhiệm vụ lưu trữ data để xử lý trên chương trình (Nếu source webapp nhỏ thì sẽ khai báo luôn trên source còn nếu source webapp lớn thì thường sẽ khai báo trong một library tên là Domain).
    10. Thư mục Areas : có chức năng tương tự như thư mục Views cũng dùng chứa các giao diện web nhưng thường dùng theo dạng module (tức là sẽ được code gọi và implement, không thể thấy trực tiếp khi truyền url).
    11. Thư mục Components : có chức năng tương tự như thư mục Areas nhưng với quy mô nhỏ hơn. Chỉ dùng chứa 1 số module chức năng nhỏ.
    12. Thư mục Helpers : nơi chứa những class và những hàm xử lý dùng lại nhiều lần.
    13. Thư mục Constants : nơi chứa những hằng số - những giá trị không thay đổi được định nghĩa rỏ ràng.
    14. Thư mục Extentions : nơi chứa những phương thức và class thuộc dạng static.
    15. Thư mục Entites : nơi chứa những class là thực thể chứa dữ liệu được đồng bộ với cơ sở dữ liệu.
    16. Thư mục Configs hay Configurations : nơi chứa những class dùng để cấu hình cho webapp.
    16. File <File_Name>Context.cs : là những file chứa DbContext dùng cho Entity Framework cấu hình connection tới cơ sở dữ liệu.

## FORMAT CODE