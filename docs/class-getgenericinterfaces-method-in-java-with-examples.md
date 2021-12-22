# Java 中的类 getGenericInterfaces()方法，示例

> 原文:[https://www . geesforgeks . org/class-getgenericinterfaces-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getgenericinterfaces-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getGenericInterfaces()** 方法用于获取该实体直接实现的接口类型。该实体可以是类或接口。方法返回由该实体直接实现的接口类型的数组。

**语法:**

```
public Type[] getGenericInterfaces()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个由该实体直接实现的接口类型为的**数组。**

下面的程序演示了 getGenericInterfaces()方法。

**例 1:**

```
// Java program to demonstrate
// getGenericInterfaces() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the type of interfaces of myClass
        // using getGenericInterfaces() method
        System.out.println(
            "GenericInterfaces of myClass: "
            + Arrays.toString(
                  myClass.getGenericInterfaces()));
    }
}
```

**输出:**

```
Class represented by myClass: class Test
GenericInterfaces of myClass: []

```

**例 2:**

```
// Java program to demonstrate
// getGenericInterfaces() method

import java.util.*;

interface Arr {
}

public class Test implements Arr {

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object
        Class myClass = Class.forName("Test");

        // Get the type of interfaces of myClass
        // using getGenericInterfaces() method
        System.out.println(
            "GenericInterfaces of myClass: "
            + Arrays.toString(
                  myClass.getGenericInterfaces()));
    }
}
```

**输出:**

```
GenericInterfaces of myClass: [interface Arr]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getGenericInterfaces–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getGenericInterfaces--)