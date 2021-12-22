# 构造函数和方法的区别

> 原文:[https://www . geeksforgeeks . org/构造函数和方法的区别/](https://www.geeksforgeeks.org/difference-between-the-constructors-and-methods/)

[Java](https://www.geeksforgeeks.org/java/) 是一种纯粹的 [OOPS 概念](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)为基础的编程语言。因此在 Java 中，所有的[变量](https://www.geeksforgeeks.org/variables-in-java/)，数据和语句都必须存在于类中。这些[类](https://www.geeksforgeeks.org/understanding-classes-and-objects-in-java/)由[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)和[方法](https://www.geeksforgeeks.org/methods-in-java/)组成。方法和构造函数在很多方面是不同的。

**[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)** :
构造函数用于初始化对象的状态。像[方法](https://www.geeksforgeeks.org/methods-in-java/)一样，构造函数也包含在对象创建时执行的**语句集合(即指令)**。每次使用 **new()** 关键字创建对象时，至少调用一个构造函数(可以是默认构造函数)来为同一类的**数据成员**分配初始值。

**例**:

```
// Java Program to illustrate constructor

import java.io.*;

class Geek {
    int num;
    String name;

    // This would be invoked while an object
    // of that class created.
    Geek()
    {
        System.out.println("Constructor called");
    }
}

class GFG {
    public static void main(String[] args)
    {
        // this would invoke default constructor.
        Geek geek1 = new Geek();

        // Default constructor provides the default
        // values to the object like 0, null
        System.out.println(geek1.name);
        System.out.println(geek1.num);
    }
}
```

**Output:**

```
Constructor called
null
0

```