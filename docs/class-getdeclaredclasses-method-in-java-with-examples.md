# Java 中的 Class getDeclaredClasses()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredclasses-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredclasses-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getDeclaredClasses()** 方法用于获取该类的类，这些类是私有的、公共的、受保护的或默认的类及其成员，而不是继承的类。方法以类对象数组的形式返回该类的类。

**语法:**

```java
public Class[] getDeclaredClasses()
               throws SecurityException

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法以 class 对象数组的形式返回这个类的**类**。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getDeclaredClasses()方法。

**例 1:**

```java
// Java program to demonstrate
// getDeclaredClasses() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the classes of myClass
        // using getDeclaredClasses() method
        System.out.println(
            "DeclaredClasses of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredClasses()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
DeclaredClasses of myClass: []

```

**例 2:**

```java
// Java program to demonstrate
// getDeclaredClasses() method

import java.util.*;

class Main {

    private class Arr {
    };

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the classes of myClass
        // using getDeclaredClasses() method
        System.out.println(
            "DeclaredClasses of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredClasses()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Main
DeclaredClasses of myClass: [class Main$Arr]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getDeclaredClasses–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredClasses--)