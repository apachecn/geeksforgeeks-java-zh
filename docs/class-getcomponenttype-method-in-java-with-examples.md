# Java 中的类 getComponentType()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getcomponent type-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getcomponenttype-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getComponentType()** 方法用于获取代表数组组件类型的类，如果这个类代表一个的话。否则返回 null。

**语法:**

```
public Class getComponentType()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回代表数组的组件类型的**类**，如果这个类代表一个的话。否则返回 null。

下面的程序演示了 getComponentType()方法。

**例 1:**

```
// Java program to demonstrate getComponentType() method

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
        // using getComponentType() method
        System.out.println("ComponentType of myClass: "
                           + myClass.getComponentType());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
ComponentType of myClass: null

```

**例 2:**

```
// Java program to demonstrate getComponentType() method

import java.util.*;

public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        int[] Arr = new int[5];

        // returns the Class object
        Class arrClass = Arr.getClass();

        // Get the ComponentType of arrClass
        // using getComponentType() method
        System.out.println("ComponentType of myClass: "
                           + arrClass.getComponentType());
    }
}
```

**输出:**

```
ComponentType of myClass: int

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getComponentType–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getComponentType--)