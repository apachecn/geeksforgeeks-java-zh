# 用示例在 Java 中类 getResource()方法

> 原文:[https://www . geesforgeks . org/class-getresource-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getresource-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getResource()** 方法用于获取该类指定资源的资源。方法以 URL 对象的形式返回此类的指定资源。

**语法:**

```
public URL getResource(String resourceName)

```

**参数:**这个方法接受一个参数 **resourceName** ，这个参数就是要获取的资源。

**返回值:**该方法以 URL 对象的形式返回该类的指定**资源**。

**异常**此方法抛出:

*   **null pointer exception** If the name is empty

下面的程序演示了 getResource()方法。

**例 1:**

```
// Java program to demonstrate
// getResource() method

import java.util.*;

public class Test {

    public int obj = 10;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        String resourceName = "obj";

        // Get the resource of myClass
        // using getResource() method
        System.out.println(
            resourceName + " resource of myClass: "
            + myClass.getResource(resourceName));
    }
}
```

**输出:**

```
Class represented by myClass: class Test
obj resource of myClass: null

```

**例 2:**

```
// Java program to demonstrate
// getResource() method

import java.util.*;

class Main {

    private Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        String resourceName = "obj";

        try {
            // Get the resource of myClass
            // using getResource() method
            System.out.println(
                resourceName + " resource of myClass: "
                + myClass.getResource(resourceName));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Class represented by myClass: class Main
obj resource of myClass: null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getResource-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getResource-java.lang.String-)