---
title: "Cấu trúc rẽ nhánh if else trong java"
description: "Mệnh đề if-else trong java được sử dụng để kiểm tra giá trị dạng boolean của điều kiện, mệnh đề này trả về giá trị đúng hoặc sai để điều kiện cho phép ta điều khiển luồng thực hiện của chương trình"
keywords:
  [
    "if",
    "else",
    "java",
    "bài tập if else trong java",
    "câu lệnh if else trong java",
    "câu lệnh if then else trong java",
    "if else if trong java",
    "if else rút gọn java",
    "if else trong java",
    "if else java",
    "java co ban",
    "java nâng cao",
    "hoc java co ban",
  ]
author:
  fullname: Techmely Team
  username: Techmely Team
  avatar: "/configs/author/logo.jpg"
chapter:
  name: "Nhập môn Java"
  slug: "chuong-02-nhap-mon-java"
category:
  logo: "/language/java.png"
  name: "Java"
  slug: "java"
  description: "Học Java từ cơ bản đến thông thạo cho mọi đối tượng"
image: https://user-images.githubusercontent.com/29374426/126427809-717c3eb0-ffba-4fa5-8e52-ec12ad9b548d.png
position: 17
---

Chương trình là một dãy các câu lệnh được bố trí thực hiện theo một trình tự nào đó, nhưng đôi khi ta muốn điều khiển luồng thực hiện của chương trình tuỳ thuộc vào điều kiện gì đó. Ngôn ngữ lập trình java cung cấp một số câu điều kiện cho phép ta điều khiển luồng thực hiện của chương trình, chúng được liệt kê trong bảng sau:

| Kiểu lệnh  | Từ khoá                         |
| ---------- | ------------------------------- |
| Lặp        | while, do-while, for            |
| Quyết định | if-else, switch-case            |
| Xử lý lỗi  | try-catch-finally, throw        |
| Rẽ nhánh   | break, continue, label:, return |

Bài này chúng ta sẽ cùng nhau tìm hiểu về cấu trúc rẽ nhánh if else trong Java.

## Hiểu về cấu trúc if-else trong Java

Trong cuộc sống của chúng ta thì gặp khá nhiều trường hợp `if-else`, ví dụ như: _"Nếu hôm nay trời mưa thì tôi sẽ nghỉ học nếu không thì tôi sẽ đi học"_. Trong lập trình cũng sẽ có câu lệnh diễn đạt ý tương tự, người ta gọi là câu điều kiện if else. Với ví dụ này thì trong Java chúng ta có thể diễn đạt như sau:

```java
if(hôm nay trời mưa) {
  tôi sẽ nghỉ học;
} else {
  tôi sẽ đi học;
}
```

## Cấu trúc rẽ nhánh if else trong Java

Trong Java có 2 cấu trúc rẽ nhánh if là **dạng khuyết** và **dạng đủ**

### Cấu trúc rẽ nhánh if else dạng khuyết

Cú pháp:

```java
if(điều kiện) {
  câu lệnh 1;
  câu lệnh 2;
  câu lệnh 3;
  ...
}
// hoặc
if(điều kiện) câu lệnh 1; // đối với trường hợp có 1 câu lệnh có thể viết tắt.
```

Sự hoạt động của cấu trúc if thiếu được mô ta qua sơ đồ sau

![Cấu trúc rẽ nhánh dạng khuyết trong java](https://user-images.githubusercontent.com/29374426/125040208-92bb7200-e0c1-11eb-9781-bc65864c5b23.png)

<div class="example"></div>

```java
public class Thaycacac {
  public static void main(String []args) {
    if(isTroiMua() === true) { // isTroiMua() là một hàm
      System.out.println("Tôi sẽ nghỉ học")
    }
  }
}
```

### Cấu trúc rẽ nhánh if else dạng đủ

Cú pháp:

```java
if(điều kiện) {
 câu lệnh 1;
 câu lệnh 2;
 câu lệnh 3;
 ...
};
else {
  câu lệnh 1;
  câu lệnh 2;
  câu lệnh 3;
 ...
}

// hoặc
if(điều kiện) câu lệnh 1;
else câu lệnh 1;
```

Sự hoạt động của cấu trúc `if-else` thiếu được mô ta qua sơ đồ sau

![Cấu trúc rẽ nhánh dạng đủ trong java](https://user-images.githubusercontent.com/29374426/125040287-a7980580-e0c1-11eb-89cf-97da184f33cf.png)

<div class="example"></div>

```java
public class Thaycacac {
  public static void main(String []args) {
    int age = 18;
    if (age > 18)
      System.out.print("Bạn đủ tuổi để đăng ký");
    else
      System.out.print("Bạn chưa đủ tuổi để đăng ký");
  }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Bạn đủ tuổi để đăng ký</code>
  </div>
</div>

### Dạng if..else if..else

Đây là dạng cấu trúc rẽ nhiều nhánh nếu ta muốn xét nhiều trường hợp để thực hiện rõ ràng hơn.

**Cú pháp:**

```java
if (điều kiện 1) {
  câu lệnh 1;
  câu lệnh 2;
  ...
} else if (điều kiện 2) {
  câu lệnh 1;
  câu lệnh 2;
  ...
} else {
  câu lệnh 1;
  câu lệnh 2;
  ...
}
```

<div class="example"></div>

```java
public class Thaycacac {
  public static void main(String []args) {
    String job = "Sinh viên";
    if (job == "Học sinh")
      System.out.print("Bạn còn lứa tuổi học sinh");
    else if (job == "Sinh viên")
      System.out.print("Sinh viên có thể tham gia");
    else
      System.out.print("Không rõ công việc của bạn");
  }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Sinh viên có thể tham gia</code>
  </div>
</div>

### Một số ví dụ cấu trúc rẽ nhánh if else

<div class="example">Kiểm tra số nhập vào là số âm hay số dương</div>

```java
  public static void checkNumber(int number) {
    if (number < 0) {
      System.out.println(number + " la so am");
    } else {
      System.out.println(number + " la so duong");
    }
  }
```

<div class="example">In ra số lớn hơn bởi 2 số người dùng nhập vào</div>

```java
public static void getMax(int number1, int number2) {
  if (number1 > number2) {
    System.out.println("so thu nhat lon hon so thu 2");
  } else if (number1 < number2) {
    System.out.println("so thu nhat nho hon so thu 2");
  } else {
    System.out.println("so thu nhat bang so thu 2");
  }
}
```

<div class="example">Kiểm tra sẽ xem năm người dùng nhập vào có phải là năm nhuận hay không</div>

```java
public static void checkLeapYear(int year) {
  if (year % 400 == 0 || (year % 4 == 0 && year % 100 != 0)) {
    System.out.println("nam " + year + " la nam nhuan");
  } else {
    System.out.println("nam " + year + " la nam khong nhuan");
  }
}
```
