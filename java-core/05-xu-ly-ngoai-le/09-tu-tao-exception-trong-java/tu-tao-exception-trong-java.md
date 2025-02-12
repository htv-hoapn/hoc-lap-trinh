---
title: "Tự tạo exception trong java"
description: "Tự tạo exception (Custom Exception) là ngoại lệ do bạn tự định nghĩa hay bạn tự tạo riêng cho mình, custom Exception trong Java được sử dụng để tùy biến ngoại lệ theo yêu cầu của người dùng"
keywords: ["custom exception trong java", "Tự tạo exception trong java"]
author:
  fullname: Techmely Team
  username: Techmely Team
  avatar: "/configs/author/logo.jpg"
chapter:
  name: "Xử lý ngoại lệ"
  slug: "chuong-05-xu-ly-ngoai-le"
category:
  logo: "/language/java.png"
  name: "Java"
  slug: "java"
  description: "Học Java từ cơ bản đến thông thạo cho mọi đối tượng"
image: http://3.bp.blogspot.com/-q1b3Acf-2P8/VfaC9Ut1ZiI/AAAAAAAAHgk/Ex0j4ze5FSk/s1600/ExceptionClassHierarchy.png
position: 9
---

Tự tạo exception (Custom Exception) là ngoại lệ do bạn tự định nghĩa hay bạn tự tạo riêng cho mình. Custom Exception trong Java được sử dụng để tùy biến ngoại lệ theo yêu cầu của người dùng. Bởi sự giúp đỡ của loại ngoại lệ này, bạn có thể có riêng kiểu và thông điệp ngoại lệ cho mình.

<div class="example">Tạo một custom exception</div>

```java
// File: InvalidAgeException.java
class InvalidAgeException extends Exception {
    InvalidAgeException(String s) {
        super(s);
    }
}
```

```java
// File: TestCustomException1.java
class TestCustomException1 {

    static void validate(int age) throws InvalidAgeException {
        if (age < 18)
            throw new InvalidAgeException("not valid");
        else
            System.out.println("welcome to vote");
    }

    public static void main(String args[]) {
        try {
            validate(13);
        } catch (Exception m) {
            System.out.println("Exception occured: " + m);
        }

        System.out.println("rest of the code...");
    }
}
```

<div class="window">
  <div class="window-header">
    <div class="action-buttons"></div>
    <span class="title-popup">Kết quả</span>
  </div>
  <div class="window-body">
    <code>Output:Exception occured: InvalidAgeException:not valid rest of the code...</code>
  </div>
</div>
