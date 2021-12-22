# 说明默认情况下超级类的默认构造函数对子类的可用性的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-scheme-availability-of-default-constructor-of-the-super-class-to-sub-class-by-default/](https://www.geeksforgeeks.org/java-program-to-illustrate-the-availability-of-default-constructor-of-the-super-class-to-the-sub-class-by-default/)

Java 中的[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)是一种用于初始化对象的特殊方法。每当使用 new()关键字创建对象时，至少会调用一个构造。构造函数名称必须与类名匹配，并且不能有返回类型。如果在这种情况下类中没有可用的构造函数，java 编译器默认提供一个**默认构造函数(无参数构造函数)**。

**T2**默认构造函数(无参数构造函数)的目的是什么

[默认构造函数](https://www.geeksforgeeks.org/g-fact-50/)用于根据类型为对象提供默认值，如 0、null 等。

**默认构造函数示例**

在下面给出的代码中，我们创建了一个名为 default constructor 的类，在这个类中，我们创建了一个 default Constructor。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate default constructor

import java.io.*;
class defaultConstructor {
    int a;
    double d;
    String s;

    // creating default constructor
    defaultConstructor()
    {
        System.out.println("Hi I am a default constructor");
    }
}
class GFG {
    public static void main(String[] args)
    {
        // creating an object of class defaultConstructor
        // after creating an object it will invoke the
        // default constructor
        defaultConstructor obj = new defaultConstructor();

        // defalult constructor provide default values to
        // the object
        System.out.println(obj.a);
        System.out.println(obj.d);
        System.out.println(obj.s);
    }
}
```

**Output**

```java
Hi I am a default constructor
0
0.0
null
```

**默认情况下超级类的默认构造函数对子类的可用性。**

当我们从父类继承到子类时，必须首先在子类构造函数中调用关键字 super()。**如果在子类构造函数中没有调用 super()，那么 java 编译器会为我们这样做**。这就是为什么每当我们创建子类的对象时，父类构造函数也会被调用。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate the Availability of Default
// Constructor of the Super Class to the Sub Class by
// Default

import java.io.*;

// creating parent class
class parent {

    // default constructor of parent class
    parent()
    {
        System.out.println(
            "I am default constructor from parent class");
    }
}

// creating child class and inheriting parent class to the
// child class
class child extends parent {

    // default constructor of child class
    child()
    {
        System.out.println(
            "I am default constructor from child class");
    }
}
class GFG {
    public static void main(String[] args)
    {
        // creating object of parent class and this will
        // only invoke parent class default constructor
        parent obj1 = new parent();

        // creating object of child class and this will
        // invoke parent class constructor first and then it
        // will invoke child class constructor
        child obj2 = new child();
    }
}
```

**Output**

```java
I am default constructor from parent class
I am default constructor from parent class
I am default constructor from child class
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate the Availability of Default
// Constructor of the Super Class to the Sub Class by
// Default

import java.util.*;

class z {

    // default constructor of class z
    z() { System.out.println("Hi I am z"); }
}

class y extends z {

    // default constructor of class y
    y() { System.out.println("Hi I am y"); }
}
class x extends y {

    // default constructor of class x
    x() { System.out.println("Hi I am x"); }
}

class GFG {

    public static void main(String[] args)
    {
        // creating an object of class x
        // this will invoke the constructor of x
        // but before invoking the constructor of class x
        // it will invoke the constructor of it's parent
        // class which is y but y is child of z class so,
        // before invoking the constructor of y class it
        // will invoke the constructor of z class(parent of
        // y class)
        x obj = new x();
    }
}
```

**Output**

```java
Hi I am z
Hi I am y
Hi I am x
```

**例 3:**

在这里，我们只想展示关键字 super()的用法，它是如何工作的

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate the Availability of Default
// Constructor of the Super Class to the Sub Class by
// Default

import java.util.*;

class z {

    // default constructor of class z
    z() { System.out.println("Hi I am z"); }
}
class y extends z {

    // default constructor of class y
    y()
    {
        // keyword super() is called by java compiler by
        // default in case of default constructor
        super();

        System.out.println("Hi I am y");
    }
}
class x extends y {

    // default constructor of class x
    x()
    {
        // keyword super() is called by java compiler by
        // default in case of default constructor
        super();
        System.out.println("Hi I am x");
    }
}

class GFG {

    public static void main(String[] args)
    {
        // creating an object of class x
        // this will invoke the constructor of x
        // but before invoking the constructor of class x
        // it will invoke the constructor of it's parent
        // class which is y but y is child of z class so,
        // before invoking the constructor of y class it
        // will invoke the constructor of z class(parent of
        // y class)
        x obj = new x();
    }
}
```

**Output**

```java
Hi I am z
Hi I am y
Hi I am x
```