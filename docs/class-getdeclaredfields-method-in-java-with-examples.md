# Java 中的类 getDeclaredFields()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredfields-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredfields-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getDeclaredFields()** 方法用于获取该类的字段，这些字段是私有、公共、受保护或默认的字段及其成员，而不是继承的字段。方法以字段对象数组的形式返回该类的字段。

**语法:**

```java
public Field[] getDeclaredFields()
               throws SecurityException

```

**参数:**此方法不接受任何参数。

**返回值:**该方法以 Field 对象数组的形式返回该类的字段。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getDeclaredFields()方法。

**例 1:**

```java
// Java program to demonstrate getDeclaredFields() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the fields of myClass
        // using getDeclaredFields() method
        System.out.println(
            "DeclaredFields of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredFields()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
DeclaredFields of myClass: []

```

**例 2:**

```java
// Java program to demonstrate getDeclaredFields() method

import java.util.*;

class Main {

    public Object obj;

    Main()
    {

        class Arr {
        };

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the fields of myClass
        // using getDeclaredFields() method
        System.out.println(
            "DeclaredFields of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredFields()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Main
DeclaredFields of myClass: [public java.lang.Object Main.obj]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getDeclaredFields–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredFields--)