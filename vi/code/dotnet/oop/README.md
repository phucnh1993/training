# OOP - Lập trình hướng đối tượng
- Lập trình hướng đối tượng là một kiểu lập trình sẽ đóng gói gom vào 1 đối tượng (object) để thỏa mãn các tính chất của đối tượng.
- Lập trình hướng đối tựng giúp chương trình chạy nhanh hơn và dễ thực thi hơn (do gom thành đối tượng nên nó gọn hơn, khi dùng đối tượng nào thì tạo đúng đối tượng đó thôi).
- Cung cấp cấu trúc hệ thống rõ ràng.
- Tăng khả năng tái sử dụng code, vòng đời phát triển phần mềm ngắn hơn.

##### TIP
- Nguyên lý “Don’t Repeat Yourself” (DRY) giúp giảm việc lặp lại code. Chúng ta nên tách những đoạn code có chung logic, đặt chúng vào chung một nơi để có thể tái sử dụng thay vì viết lại đoạn code tương tự.

## CLASS - OBJECT
- Class (Lớp) và Object (đối tượng) là hai khái niệm chính trong lập trình hướng đối tượng.
- Ví dụ ta có class **Fruit** nhưng có các Object là **Apple**, **Banana**, **Mango** hay có class **Car** nhưng có các Object là **Volvo**, **Audi**, **Toyota**.
- Có thể coi **Class** như một *template* - khuôn mẫu cho nhiều **Object**, và một **Object** như là một *instance* - thực thể của **Class**.
- Tạo một Class với 1 Property x:
```C#
public class Car {
  int x = 5;
}
```
- Khai báo đối tượng của lớp:
```C#
Car audi = new Car();
```
- **Class Method** : tương đương với 1 function - hàm nhưng lại thuộc quyền quản lý của Class (tức là khai báo đối tượng mới gọi được).
```C#
public class Car {
  public void myMethod() {
    Console.Write("Hello World!");
  }
}

public class Main {
  public static void main(String[] args) {
    Car audi = new Car();
    audi.myMethod(); // Kết quả là "Hello World"
  }
}
```
- **Constructor** : Phương thức khai báo của 1 Class. Dùng khởi tạo 1 Object và truyền data vào Properties.
```C#
public class Car {
  int x; 
  // Tạo constructor
  public Car() {
    x = 5;  // Thiết lập giá trị ban đầu cho attribute x
  }
}
public class Main {
  public static void main(String[] args) {
    Car audi = new Car(); // Constructor được thực thi
    Console.Write(audi.x); // In ra giá trị của x là 5
  }
}
```
##### Lưu ý
- **Constructor** phải trùng với tên **Class**, và không có **return type**.
- Cũng lưu ý rằng **Constructor** được thực thi khi khởi tạo **Object**.
- Tất cả **Class** điều có **default constructor**: Nếu không tạo **constructor** bên trong **Class**, thì class sẽ dùng **default constructor**. Tuy nhiên, sau đó không thể thiết lập giá trị mặc định cho các Property trong class.
- **Constructors** có thể chứa các parameters (tham số), những parameters này được dùng để khởi tạo giá trị ban đầu cho các Properties.
```C#
public class Car {
  int x; 
  public Car(int y) {
    x = y;
  }
}
public class Main {
  public static void main(String[] args) {
    Car audi = new Car(5);
    Console.Write(audi.x); // Kết quả: 5
  }
}
```
- **final** : Class không thể được kế thừa bởi các class khác. Attribute và method không thể được overridden(ghi đè) hoặc chỉnh sửa.
- **abstract** : Class không được dùng để tạo object. Để sử dụng abstract class, nó phải được kế thừa từ class khác. Abstract method không có body. Body của abstract method chỉ được định nghĩa bởi subclass sau khi kế thừa
- **static** : Attribute và method thuộc về class, chứ không phải thuộc về object.
- Trong .NET public variable gọi là Property.

## 4 Tính chất của lập trình hướng đối tượng
### Encapsulation - Tính đóng gói
Encapsulation đảm bảo dữ liệu nhạy cảm bị ẩn đi từ phía người dùng. Để thực hiện điều này, bạn phải:
- Khai báo private cho các variable/attribute.
- Khai báo public cho các get và set method để truy cập và chỉnh sửa giá trị của các private variable/attribute.

#### GET - SET
- private attribute chỉ có thể được truy cập bên trong class. Tuy nhiên, chúng ta có thể truy cập bằng cách khai báo get và set method.
- get method trả về giá trị của attribute, và set method dùng để gán giá trị cho attribute.
```C#
public class Person {
  private String name; // private = restricted access
  // Getter
  public String getName() {
    return name;
  }
  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}
```
- Lợi ích:
    1. Kiểm soát attribute và method tốt hơn.
    2. Linh động: lập trình viên có thể thay đổi một phần code mà không ảnh hưởng đến những phần code còn lại.
    3. Tăng tính bảo mật cho dữ liệu.

### Inheritance - Tính kế thừa
Có thể kế thừa toàn bộ attribute và method từ một class sang một class khác. Chúng ta chia khái niệm inheritance thành hai nhóm:
- **subclass** (class con) – là class kế thừa class khác.
- **superclass** (class cha) – là class được kế thừa.
```C#
class Vehicle {
  protected String brand = "Ford";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    Console.Write("Tuut, tuut!");
  }
}
class Car : Vehicle {
  private String modelName = "Mustang";    // Car attribute
}
```
- Tăng tính tái sử dụng code: sử dụng lại các attribute và method của class có sẵn khi bạn muốn tạo một class mới.

### Polymorphism - Tính đa hình
Như đã nói ở trên, **Inheritance** là kế thừa các attribute và method từ một class sang một class khác. Còn **Polymorphism** là sử dụng một method để thể hiện nhiều chức năng khác nhau.
- Ví dụ: *Animal* là superclass có method **animalSound()**. Subclass của *Animal* là *Pig*, *Dog*.
```C#
class Animal {
  public void animalSound() {
    Console.Write("The animal makes a sound");
  }
}
class Pig : Animal {
  public void animalSound() {
    Console.Write("The pig says: wee wee");
  }
}
class Dog : Animal {
  public void animalSound() {
    Console.Write("The dog says: bow wow");
  }
}
```
### Abstraction - Tính trừu tượng
- **Abstraction** là quá trình ẩn các chi tiết cụ thể và hiển thị những thông tin cần thiết đến người dùng.
- **Abstraction** có thể được thực hiện thông qua **abstract classe** hoặc **interface**.
- Từ khoá **abstract** là một **non-access modifier**, được sử dụng cho class và method:
    1. **Abstract class**: là một class đặc biệt không thể được dùng để khởi tạo object (Để sử dụng được abstract class, nó phải được kế thừa từ một class khác).
    2. **Abstract method**: chỉ được sử dụng trong abstract class, và nó không có body. Body chỉ được khai báo trong subclass.
- Trong một abstract class có thể có cả abstract method và các method thông thường khác.
- Những lưu ý khi sử dụng Interface:
    1. Như abstract class, interface không thể được dùng để khởi tạo object.
    2. Method trong interface không có body – body chỉ được định nghĩa trong class implement interface.
    3. Interface không có constructor.
- Sử dụng interface để thực hiện việc bảo mật – ẩn các chi tiết không cần thiết và chỉ hiển thị những chi tiết quan trọng của object.