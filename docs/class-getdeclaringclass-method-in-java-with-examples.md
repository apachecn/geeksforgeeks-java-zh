# Java 中的 Class getDeclaringClass()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaringclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaringclass-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getDeclaringClass()** 方法用于获取该类的声明类。如果此类或接口是另一个类的成员，则方法返回此类的声明类。否则此方法返回 null。

**语法:**

```java
public Constructor getDeclaringClass()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类或接口是另一个类的成员，这个方法返回这个类的**声明类**。否则此方法返回 null。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getDeclaringClass()方法。

**例 1:**

```java
// Java program to demonstrate getDeclaringClass() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the declaring class of myClass
        // using getDeclaringClass() constructor
        System.out.println("DeclaringClass of myClass: "
                           + myClass.getDeclaringClass());
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
DeclaringClass of myClass: null

```

**例 1:**

```java
// Java program to demonstrate getDeclaringClass() method

import java.util.*;

class Main {

    class Arr {
    };

    public Object obj;

    Main()
    {

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        // Get the declaring class of myClass
        // using getDeclaringClass() constructor
        System.out.println("DeclaringClass of myClass: "
                           + myClass.getDeclaringClass());
    }
}
```

**输出:**

```java
DeclaringClass of myClass: class Main

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getDeclaringClass–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaringClass--)