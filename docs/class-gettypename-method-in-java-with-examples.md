# Java 中的 Class getTypeName()方法，带示例

> 原文:[https://www . geesforgeks . org/class-gettypename-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-gettypename-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getTypeName()** 方法用于获取该类的类型名，提供该类的类型信息。方法以字符串的形式返回此类的类型名。

**语法:**

```
public String getTypeName()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法以字符串的形式返回该类的**类型名**。

下面的程序演示了 getTypeName()方法。

**例 1:**

```
// Java program to demonstrate getTypeName() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the type name of myClass
        // using getTypeName() method
        System.out.println("TypeName of myClass: "
                           + myClass.getTypeName());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
TypeName of myClass: Test

```

**例 2:**

```
// Java program to demonstrate getTypeName() method

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

        // Get the type name of myClass
        // using getTypeName() method
        System.out.println("TypeName of myClass: "
                           + myClass.getTypeName());
    }
}
```

**输出:**

```
TypeName of myClass: Main$1Arr

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getTypeName–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getTypeName--)