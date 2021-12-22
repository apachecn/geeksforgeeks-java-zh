# 使用构造函数分配和初始化超类成员的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-allocate-initialize-super-class-members-use-constructor/](https://www.geeksforgeeks.org/java-program-to-allocate-and-initialize-super-class-members-using-constructor/)

Java 中的[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)是一种用于初始化对象的特殊方法。每当使用[新](https://www.geeksforgeeks.org/new-operator-java/)关键字创建对象时，至少会调用一个构造。构造函数名称必须与类名匹配，并且不能有返回类型。如果在这种情况下类中没有可用的构造函数，java 编译器默认提供默认构造函数(没有参数构造函数)。

**参数化构造函数:**参数化构造函数用于用我们自己的值初始化类的字段。

**例:**

## 爪哇

```java
// Parameterized Constructor Example in Java

import java.io.*;
class parameterizedConstructor {

    // fields of the class
    String name;
    int regestrationNumber;

    // creating a parameterized constructor so that we can
    // initialize the value of the class
    parameterizedConstructor(String name,
                             int regestrationNumber)
    {
        System.out.println("constructor call");
        this.name = name;
        this.regestrationNumber = regestrationNumber;
    }
}

class GFG {
    public static void main(String[] args)
    {
        // creating our first object
        parameterizedConstructor obj1
            = new parameterizedConstructor("Nilesh",
                                           2021806);
        System.out.println("Name of the student "
                           + obj1.name);
        System.out.println("Registration Number "
                           + obj1.regestrationNumber);

        // creating second object
        parameterizedConstructor obj2
            = new parameterizedConstructor("Bhaskar",
                                           2021807);
        System.out.println("Name of the student "
                           + obj2.name);
        System.out.println("Registration Number "
                           + obj2.regestrationNumber);
    }
}
```

**输出**

```java
constructor call
Name of the student Nilesh
Registration Number 2021806
constructor call
Name of the student Bhaskar
Registration Number 2021807
```