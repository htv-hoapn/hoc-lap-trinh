---
title: "Từ khóa static trong Java"
description: "Bài này chúng ta sẽ tìm hiểu về Thuộc tính tĩnh (static variable), tự học lập trình java, chia sẻ kiến thức về java"
keywords:
  [
    "biến static trong java",
    "biến static và final trong java",
    "biến static và hàm static trong java",
    "class static trong java",
    "code static trong java",
    "câu lệnh static trong java",
    "final static trong java",
    "hàm static trong java",
    "khi nào dùng static trong java",
    "khối static trong java",
    "từ khóa static trong java",
    "từ khóa static trong java code",
    "từ khóa static trong java fpt",
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
image: https://user-images.githubusercontent.com/29374426/131236350-539f5fcf-79f4-43ed-8d38-35494726df1a.png
position: 11
---

Từ khóa **static** trong Java được sử dụng chính để quản lý bộ nhớ. Chúng ta có thể áp dụng từ khóa **static** với các biến, các phương thức, các khối, các lớp lồng nhau(nested class). Từ khóa static thuộc về lớp chứ không thuộc về instance(thể hiện) của lớp.

- **Biến static**: Khi bạn khai báo một biến là static, thì biến đó được gọi là biến tĩnh, hay biến static.
- **Phương thức static**: Khi bạn khai báo một phương thức là static, thì phương thức đó gọi là phương thức static.
- **Khối static**: Được sử dụng để khởi tạo thành viên dữ liệu static.

![image](https://user-images.githubusercontent.com/29374426/131236350-539f5fcf-79f4-43ed-8d38-35494726df1a.png)

## Biến static trong Java

Biễn được khai báo với từ khoá static gọi là biến tĩnh, và chúng có đặc điểm sau:

- Biến static có thể được sử dụng để tham chiếu thuộc tính chung của tất cả đối tượng (mà không là duy nhất cho mỗi đối tượng), ví dụ như tên công ty của nhân viên, tên trường học của các sinh viên, ...
- Các thuộc tính tĩnh được cấp phát một vùng bộ nhớ cố định, trong java bộ nhớ dành cho các thuộc tính tĩnh chỉ được cấp phát khi lần đầu tiên ta truy cập đến nó.

Sử dụng biến static giúp chương trình của bạn sử dụng bộ nhớ hiệu quả hơn (tiết kiệm bộ nhớ).

Ví dụ:

```java
class Student {
     int code;
     String fullname;
     String university="FPT";
}
```

Giả sử có 10000 sinh viên trong trường đại học, bây giờ instance của các dữ liệu thành viên sẽ sự dụng bộ nhớ mỗi khi đối tượng được tạo. Tất cả sinh viên có code fullname name là thuộc tính riêng. Tuy nhiên, university là thuộc tính chung của tất cả đối tượng. Nếu chúng ta tạo nó là `static`, thì trường này sẽ chỉ sử dụng bộ nhớ một lần để lưu biến này. Khi đó:

```java
public class Student {
    int code;
    String fullname;
    static String university = "FPT";

    Student(int code, String fullname) {
        code = code;
        fullname = fullname;
    }

    void display() {
        System.out.println(code + " - " + fullname + " - " + university);
    }

    public static void main(String args[]) {
        Student s1 = new Student(05740, "Hoa");
        Student s2 = new Student(05439, "Huyen");

        s1.display();
        s2.display();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>05740 - Hoa - FPT</code><br/>
    <code>05439 - Huyen - FPT</code>
  </div>
</div>

<div class="note">
Ta không thể sử dụng hàm tạo để khởi đầu các thuộc tính tĩnh, bởi vì hàm tạo không phải là phương thức tĩnh
</div>

## Phương thức static trong Java

Một phương thức được khai báo là `static` được gọi là phương thức tĩnh và chúng có đặc điểm sau:

- Một phương thức static thuộc lớp chứ không phải đối tượng của lớp.
- Một phương thức static gọi mà không cần tạo một instance của một lớp.
- Phương thức static có thể truy cập biến static và có thể thay đổi giá trị của nó.

<div class="example"></div>

```java
public class Student {
    int code;
    String fullname;
    static String university = "FPT";

    static void change() {
        // Thay đổi thuộc tính static (thuộc tính chung của tất cả các đối tượng)
        university = "Bưu Chính Viễn Thông";
    }

    Student(int code, String fullname) {
        code = code;
        fullname = fullname;
    }

    void display() {
        System.out.println(code + " - " + fullname + " - " + university);
    }

    public static void main(String args[]) {
        Student.change();

        Student s1 = new Student(05740, "Hoa");
        Student s2 = new Student(05439, "Huyen");

        s1.display();
        s2.display();
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>05740 - Hoa - Bưu Chính Viễn Thông</code><br/>
    <code>05439 - Huyen - Bưu Chính Viễn Thông</code>
  </div>
</div>

## Khối static trong Java

- Được sử dụng để khởi tạo thành viên dữ liệu static.
- Nó được thực thi trước phương thức main tại lúc tải lớp.

[Tìm hiểu kỹ hơn về khối static trong Java](/bai-viet/java/khoi-anonymous-va-static-trong-java)

<div class="example"></div>

```java
public class Student {
    static {
        System.out.println("Khối static: hello !");
    }

    public static void main(String args[]) {
        System.out.println("Main: hello !");
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Khối static: hello !</code><br/>
    <code>Main: hello !</code>
  </div>
</div>
