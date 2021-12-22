# Java 中的类 getEnclosingConstructor()方法，带示例

> 原文:[https://www . geeksforgeeks . org/class-getenclosingconstructor-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getenclosingconstructor-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的**getEnclosingConstructor()**方法用于获取该类的封闭构造函数。如果此类是在该构造函数中声明的本地类或匿名类，则方法返回此类的封闭构造函数。否则此方法返回 null。

**语法:**

```
public Constructor getEnclosingConstructor()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是一个局部类或者匿名类，这个方法返回这个类的**封闭构造函数**。否则该构造函数返回 null。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getEnclosingConstructor()方法。

**例 1:**

```
// Java program to demonstrate
// getEnclosingConstructor() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the enclosing constructors of myClass
        // using getEnclosingConstructor() constructor
        System.out.println("EnclosingConstructor of myClass: "
                           + myClass.getEnclosingConstructor());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
EnclosingConstructor of myClass: null

```

**例 2:**

```
// Java program to demonstrate
// getEnclosingConstructor() method

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

        // Get the enclosing constructors of myClass
        // using getEnclosingConstructor() constructor
        System.out.println("EnclosingConstructor of myClass: "
                           + myClass.getEnclosingConstructor());
    }
}
```

**输出:**

```
EnclosingConstructor of myClass: Main()

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getEnclosingConstructor–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getEnclosingConstructor--)