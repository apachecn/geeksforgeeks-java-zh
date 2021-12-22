# Java 中的类 isArray()方法，示例

> 原文:[https://www . geesforgeks . org/class-isarray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-isarray-method-in-java-with-examples/)

**[Java . lang . Class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **isArray()** 方法用于检查该类是否为 Array 类。如果此类是数组类，则方法返回 true。否则返回 false。

**语法:**

```
public boolean isArray()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是数组类，这个方法返回**真**。否则返回**假**。

下面的程序演示了 isArray()方法。

**例 1:**

```
// Java program to demonstrate isArray() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an array
        // using isArray() method
        System.out.println("Is Test an array: "
                           + myClass.isArray());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Is Test an array: false

```

**例 2:**

```
// Java program to demonstrate isArray() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        int[] T = new int[5];

        // Check if T is an array
        // using isArray() method
        System.out.println("Is T an array: "
                           + T.getClass().isArray());
    }
}
```

**输出:**

```
Is T an array: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # isArray–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isArray--)