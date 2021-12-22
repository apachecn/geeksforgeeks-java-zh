# Java 中的 Class getClasses()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getclasses-method-in-java-with-examples/)

[**Java . lang . class**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)的 **getClasses()** 方法用于获取该类的类，这些类是公共的类和接口及其成员。方法以类对象数组的形式返回该类的类。
**语法:**

```java
public Class[] getClasses()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法以 class 对象数组的形式返回该类的**类**。
**异常**如果有安全管理人员在场且不满足安全条件，此方法抛出**安全异常**。
下面的程序演示了 getClasses()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getClasses() method

import java.util.*;

public class Test {
    public class Arr {
    };

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the classes of myClass
        // using getClasses() method
        System.out.println("Classes of myClass: "
                           + Arrays.toString(
                                 myClass.getClasses()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Classes of myClass: [class Test$Arr]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getClasses() method

import java.util.*;

class Main {

    public Object obj;
    private class Arr {
    };

    Main()
    {
        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the classes of myClass
        // using getClasses() method
        System.out.println("Classes of myClass: "
                           + Arrays.toString(
                                 myClass.getClasses()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Main
Classes of myClass: []
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getclass–T4】