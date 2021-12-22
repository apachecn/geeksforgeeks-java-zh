# Java 中的 Class getEnclosingClass()方法，带示例

> 原文:[https://www . geeksforgeeks . org/class-getenclosingclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getenclosingclass-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getEnclosingClass()** 方法用于获取该类的封闭类。如果此类是在该类中声明的本地类或匿名类，则方法返回此类的封闭类。否则此方法返回 null。

**语法:**

```java
public Class getEnclosingClass() throws SecurityException

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是在那个类中声明的局部类或者匿名类，这个方法返回这个类的封闭类。否则此方法返回 null。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getEnclosingClass()方法。

**例 1:**

```java
// Java program to demonstrate getEnclosingClass() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the enclosing class of myClass
        // using getEnclosingClass() method
        System.out.println("EnclosingClass of myClass: "
                           + myClass.getEnclosingClass());
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
EnclosingClass of myClass: null

```

**例 2:**

```java
// Java program to demonstrate getEnclosingClass() method

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

        // Get the enclosing class of myClass
        // using getEnclosingClass() method
        System.out.println("EnclosingClass of myClass: "
                           + myClass.getEnclosingClass());
    }
}
```

**输出:**

```java
EnclosingClass of myClass: class Main

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getEnclosingClass–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getEnclosingClass--)