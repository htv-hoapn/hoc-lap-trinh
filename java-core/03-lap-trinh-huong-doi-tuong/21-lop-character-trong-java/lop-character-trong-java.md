---
title: "Lớp Character trong Java"
description: "Bài này chúng ta sẽ tìm hiểu về Một số lớp cơ bản của Java, tự học lập trình java, chia sẻ kiến thức về java"
keywords:
  [
    "character trong java",
    "lớp character java là gì",
    "lớp character trong java",
    "lớp character trong java java",
    "lớp charactor java cơ bản",
    "lớp charactor trong java 8",
    "lớp charactor trong java code",
    "lớp charactor trong java cơ bản",
    "lớp charactor trong java fpt",
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
image: https://user-images.githubusercontent.com/29374426/131965653-d093ebae-2089-4057-b718-f2e6bfb13c88.png
position: 21
---

Character class là một [Wrapper class](/bai-viet/java/lop-wrapper-trong-java) của char trong java. Cung cấp nhiều method giúp thao tác nhanh với char, ngoài ra một object Character chỉ chứa duy nhất một giá trị char.

![image](https://user-images.githubusercontent.com/29374426/131965653-d093ebae-2089-4057-b718-f2e6bfb13c88.png)

## Khởi tạo một lớp Character

Lớp Character cung cấp một số phương thức hữu ích để thao tác các ký tự. Bạn có thể tạo một đối tượng Ký tự với hàm tạo Constructor

<div class="example"></div>

```java
Character ch = new Character('a');
```

## Các phương thức trong lớp Character

![image](https://user-images.githubusercontent.com/29374426/131965698-235e0ffb-e9f9-4536-a674-7a5e12537e7a.png)

- `isLetter()`: Xác định xem giá trị char được chỉ định có phải là một chữ cái hay không.

<div class="example"></div>

```java
Character ch = new Character('a');// true
```

- `isDigit()`: Xác định xem giá trị char được chỉ định có phải là một chữ số hay không

<div class="example"></div>

```java
System.out.println(Character.isDigit('0')); // true
```

- `isWhitespace()`: Xác định xem giá trị char được chỉ định có phải là khoảng trắng hay không

<div class="example"></div>

```java
public static boolean isWhitespace(char ch)
```

- `isUpperCase()`: Xác định xem giá trị char được chỉ định là chữ hoa hay không.

<div class="example"></div>

```java
public static boolean isUpperCase(char ch)
public static boolean isUpperCase(int codepoint)
```

- `isLowerCase()`: Xác định xem giá trị char được chỉ định là chữ thường hay không.

<div class="example"></div>

```java
public static boolean isLowerCase(char ch)
public static boolean isLowerCase(int codePoint)
```

- `toUpperCase()`: Chuyển ký tự char thường thành chữ hoa.

<div class="example"></div>

```java
public static char toUpperCase(char ch)
// or
public static char toUpperCase(int codePoint)
```

- `toLowerCase()`: Chuyển ký tự char thường thành chữ hoa.

<div class="example"></div>

```java
public static char toLowerCase(char ch)
public static char toLowerCase(int codePoint)
```

- `toString()`: Chuyển ký tự char trong object Character thành chuỗi.

<div class="example"></div>

```java
public static String toString(char c)
```

- `charValue()`: Trả về char value của object Character.

<div class="example"></div>

```java
public char charValue()
```

- `equals()`: So sánh bằng 2 object Character.

<div class="example"></div>

```java
public boolean equals(Object obj)
```

- `compareTo()`: So sánh với một object Character khác dựa trên char value. Trả về số bé hơn không nếu nhỏ không, 0 – bằng, lớn hơn không nếu lớn hơn.
- `isAlphabetic()`: Kiểm tra ký tự có nằm trong khoảng a-zA-Z hay không dựa vào mã code.
- `isLetterOrDigit()`: Kiểm tra ký tự có phải là một ký tự a-zA-Z hoặc là một ký tự hay không
- `valueOf()`: Trả về một object của Character class.
