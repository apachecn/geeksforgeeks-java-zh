# Java 中的类 getSimpleName()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getsimplename-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getsimplename-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getSimpleName()** 方法用于获取这个类的简单名称，如源代码中所给。方法以字符串的形式返回这个类的简单名称。如果这个类是匿名的，那么这个方法返回空字符串。

**语法:**

```
public String getSimpleName()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法以 String 的形式返回这个类的简单名称。如果这个类是匿名的，那么这个方法返回空字符串。

下面的程序演示了 getSimpleName()方法。

**例 1:**

```
// Java program to demonstrate getSimpleName() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the simple name of myClass
        // using getSimpleName() method
        System.out.println("SimpleName of myClass: "
                           + myClass.getSimpleName());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
SimpleName of myClass: Test

```

**例 2:**

```
// Java program to demonstrate getSimpleName() method

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

        // Get the simple name of myClass
        // using getSimpleName() method
        System.out.println("SimpleName of myClass: "
                           + myClass.getSimpleName());
    }
}
```

**输出:**

```
SimpleName of myClass: Arr

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getSimpleName–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getSimpleName--)