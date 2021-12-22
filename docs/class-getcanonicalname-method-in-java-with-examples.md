# Java 中的类 getCanonicalName()方法，示例

> 原文:[https://www . geesforgeks . org/class-getcanonicalname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getcanonicalname-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getCanonicalName()** 方法用于获取这个类的规范名，这是 java 语言规范定义的规范名。方法以字符串的形式返回此类的规范名称。

**语法:**

```java
public String getCanonicalName()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法以字符串的形式返回这个类的**规范名**。

下面的程序演示了 getCanonicalName()方法。

**例 1:**

```java
// Java program to demonstrate getCanonicalName() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the canonical name of myClass
        // using getCanonicalName() method
        System.out.println("CanonicalName of myClass: "
                           + myClass.getCanonicalName());
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
CanonicalName of myClass: Test

```

**例 2:**

```java
// Java program to demonstrate getCanonicalName() method

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
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the canonical name of myClass
        // using getCanonicalName() method
        System.out.println("CanonicalName of myClass: "
                           + myClass.getCanonicalName());
    }
}
```

**输出:**

```java
Class represented by myClass: class Main$1Arr
CanonicalName of myClass: null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getCanonicalName–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getCanonicalName--)