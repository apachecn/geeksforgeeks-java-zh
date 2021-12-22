# Java 中的类 getEnclosingMethod()方法，示例

> 原文:[https://www . geeksforgeeks . org/class-getenclosingmethod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getenclosingmethod-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getEnclosingMethod()** 方法用于获取该类的封闭方法。如果该类是在该方法中声明的本地类或匿名类，则该方法返回该类的封闭方法。否则此方法返回 null。

**语法:**

```
public Method getEnclosingMethod()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是在该方法中声明的局部类或者匿名类，那么这个方法返回这个类的**封闭方法**。否则此方法返回 null。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getEnclosingMethod()方法。

**例 1:**

```
// Java program to demonstrate getEnclosingMethod() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the enclosing methods of myClass
        // using getEnclosingMethod() method
        System.out.println("EnclosingMethod of myClass: "
                           + myClass.getEnclosingMethod());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
EnclosingMethod of myClass: null

```

**例 2:**

```
// Java program to demonstrate getEnclosingMethod() method

import java.util.*;

class Main {

    public Object obj;

    public Object func()
    {
        class Arr {
        };
        return new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        Main t = new Main();

        // returns the Class object
        Class myClass = t.func().getClass();

        // Get the enclosing constructors of myClass
        // using getEnclosingConstructor() constructor
        System.out.println("getEnclosingMethod of myClass: "
                           + myClass.getEnclosingMethod());
    }
}
```

**输出:**

```
EnclosingConstructor of myClass: public java.lang.Object Main.func()

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getEnclosingMethod–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getEnclosingMethod--)