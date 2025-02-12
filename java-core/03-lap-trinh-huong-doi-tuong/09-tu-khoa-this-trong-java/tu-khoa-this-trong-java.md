---
title: "Từ khóa this trong Java"
description: "Từ khóa this trong java là một biến tham chiếu được sử dụng để tham chiếu tới đối tượng của lớp hiện tại. Biến this là một biến ẩn tồn tại trong tất cả các lớp trong ngông ngữ java"
keywords:
  [
    "biến this trong java",
    "con trỏ this trong java",
    "hàm this trong java",
    "this trong java là gì",
    "this. trong java",
    "từ khóa this",
    "từ khóa this trong java",
    "từ khóa this trong java bị lỗi",
    "từ khóa this trong java code",
    "từ khóa this trong java có nghĩa là gì",
    "từ khóa this trong java developer",
    "từ khóa this trong java development",
  ]
author:
  fullname: Techmely Team
  username: Techmely Team
  avatar: "/configs/author/logo.jpg"
chapter:
  name: "Lập trình hướng đối tượng"
  slug: "chuong-03-lap-trinh-huong-doi-tuong"
category:
  logo: "/language/java.png"
  name: "Java"
  slug: "java"
  description: "Học Java từ cơ bản đến thông thạo cho mọi đối tượng"
image: https://user-images.githubusercontent.com/29374426/131205481-bc00bbd6-82c5-4e1f-b53d-c28d00e98e0f.png
position: 9
---

Từ khóa **this** trong java là một biến tham chiếu được sử dụng để tham chiếu tới đối tượng của lớp hiện tại. Biến **this** là một biến ẩn tồn tại trong tất cả các lớp trong ngông ngữ java. Một class trong Java luôn tồn tại một biến this.

![image](https://user-images.githubusercontent.com/29374426/131205481-bc00bbd6-82c5-4e1f-b53d-c28d00e98e0f.png)

## Tham chiếu tới biến instance của lớp hiện tại.

Từ khóa **this** trong java có thể được dùng để tham chiếu tới biến instance của lớp hiện tại. Sẽ rất phức tạp nếu như có một biến toàn cục và biến cục bộ trùng tên thì từ khóa **this** sẽ giúp bạn giải quyết vấn đề này.

<div class="example">thể hiện tham chiếu tới lớp</div>

```java
public class HocSinh {

    int id;
    String name;

    HocSinh(int id, String name) {
        id = id;
        name = name;
    }

    void hienThi() {
        System.out.println(id + " " + name);
    }

    public static void main(String args[]) {
        HocSinh s1 = new HocSinh(111, "Viet");
        HocSinh s2 = new HocSinh(222, "Nam");
        s1.hienThi();
        s2.hienThi();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>0 null</code><br/>
    <code>0 null </code>
  </div>
</div>

Ở ví dụ này, tên của tham số của [constructor](/bai-viet/java/phuong-thuc-khoi-tao) `HocSinh()` trùng với tên của biến toàn cục đó là lý do tại sao cần phải sử dụng từ khóa this để phân biệt biến cục bộ và biến toàn cục. Từ khóa this sẽ giúp chúng ta giải quyết vấn đề này.

```java
public class HocSinh {

    int id;
    String name;

    HocSinh(int id, String name) {
        this.id = id;
        this.name = name;
    }

    void hienThi() {
        System.out.println(id + " " + name);
    }

    public static void main(String args[]) {
        HocSinh s1 = new HocSinh(111, "Viet");
        HocSinh s2 = new HocSinh(222, "Nam");
        s1.hienThi();
        s2.hienThi();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>111 Viet</code><br/>
    <code>222 Nam</code>
  </div>
</div>

<div class="note">
  Nếu biến cục bộ và biến toàn cục có tên khác nhau thì không cần sử dụng từ khóa this.
</div>

## Sử dụng this() gọi constructor của lớp hiện tại.

Phương thức `this()` có thể được sử dụng để gọi [constructor](/bai-viet/java/phuong-thuc-khoi-tao) của lớp hiện tại. Cách sử dụng này sẽ hữu dụng hơn nếu bạn có nhiều [constructor](/bai-viet/java/phuong-thuc-khoi-tao) trong một lớp và bạn muốn sử dụng lại.

<div class="example"></div>

```java
public class HocSinh2 {

    int id;
    String name;

    HocSinh2() {
        System.out.println("gọi constructor mặc định");
    }

    HocSinh2(int id, String name) {
        this(); // nó được sử dụng để gọi constructor của lớp hiện tại
        this.id = id;
        this.name = name;
    }

    void display() {
        System.out.println(id + " " + name);
    }

    public static void main(String args[]) {
        HocSinh2 e1 = new HocSinh2(111, "Viet");
        HocSinh2 e2 = new HocSinh2(222, "Nam");
        e1.display();
        e2.display();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>gọi Constructor mặc định</code><br/>
    <code>111 Viet</code><br/>
    <code>222 Nam</code>
  </div>
</div>

`this()` được dùng để sự dụng lại [constructor](/bai-viet/java/phuong-thuc-khoi-tao) trong [constructor](/bai-viet/java/phuong-thuc-khoi-tao) khác. Nó sẽ thừa kế các thuộc tính của [constructor](/bai-viet/java/phuong-thuc-khoi-tao) được gọi.

```java
public class HocSinh3 {

    int id;
    String name;
    String city;

    HocSinh3(int id, String name) {
        this.id = id;
        this.name = name;
    }

    HocSinh3(int id, String name, String city) {
        this(id, name);// now no need to initialize id and name
        this.city = city;
    }

    void display() {
        System.out.println(id + " " + name + " " + city);
    }

    public static void main(String args[]) {
        HocSinh3 e1 = new HocSinh3(111, "Viet");
        HocSinh3 e2 = new HocSinh3(222, "Nam", "Ha Noi");
        e1.display();
        e2.display();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>111 Viet</code><br/>
    <code>222 Nam</code>
  </div>
</div>

<div class="note">
this() phải được khai báo dòng lệnh đầu tiên trong Constructor.
</div>

### Gọi phương thức của lớp hiện tại

Bạn có thể sử dụng từ khóa `this` để gọi phương thức của lớp hiện tại. Nếu bạn không sử dụng từ khóa `this`, trình biên dịch sẽ tự động thêm từ khóa `this` cho việc gọi phương thức.

![image](https://user-images.githubusercontent.com/29374426/131204535-5cb697f9-425d-4019-af0f-e84ca1542234.png)

<div class="example"></div>

```java
public class HocSinh4 {

    void sayHello() {
        System.out.println("Hello Thaycacac");
    }

    void noiXinChao() {
        System.out.println("Xin chao Thaycacac");
        this.sayHello(); // bạn cũng có thể gọi thông qua biến this
    }

    void xinChao() {
        noiXinChao();// trình biên dịch sẽ thêm this để gọi phương thức noiXinChao()
    }

    public static void main(String args[]) {
        HocSinh4 hocSinh = new HocSinh4();
        hocSinh.xinChao();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Xin chao Thaycacac</code><br/>
    <code>Hello Thaycacac</code>
  </div>
</div>

## Sử dụng từ khóa this như một tham số của phương thức

Từ khóa `this` có thể được dùng như một tham số trong phương thức. Cách dùng này chủ yếu được sử dụng trong xử lý sự kiện.

```java
public class HocSinh5 {

    void m(HocSinh5 obj) {
        System.out.println("Hello Thaycacac");
    }

    void p() {
        m(this); // this lúc này là đối tượng học sinh
    }

    public static void main(String args[]) {
        HocSinh5 hocSinh = new HocSinh5();
        hocSinh.p();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Hello Thaycacac</code>
  </div>
</div>

Chúng ta cũng có thể truyền từ khóa `this` trong [constructor](/bai-viet/java/phuong-thuc-khoi-tao).Việc này rất hữu ích nếu chúng ta phải sử dụng một đối tượng trong nhiều lớp.

```java
class B {

    A4 obj;

    B(A4 obj) {
        this.obj = obj;
    }

    void display() {
        System.out.println(obj.data);// sử dụng biến thành viên cửa lớp A4
    }
}

class A4 {

    int data = 10;

    A4() {
        B b = new B(this);
        b.display();
    }

    public static void main(String args[]) {
        A4 a = new A4();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>10</code>
  </div>
</div>

## Sử dụng từ khóa this để trả về instance của lớp hiện tại

Chúng ta có thể trả về instance của lớp hiện tại bằng cách sử dụng từ khóa this. Trong trường hợp này, kiểu trả về của phương thức phải là kiểu class (không là kiểu nguyên thủy).

```java
class A {
    A getA() {
        return this;
    }
    void msg() {
        System.out.println("Hello Thaycacac");
    }
}

class Test1 {
    public static void main(String args[]) {
        new A().getA().msg();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Hello Thaycacac</code>
  </div>
</div>
