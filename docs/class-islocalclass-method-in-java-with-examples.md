# Java 中的 Class isLocalClass()方法，带示例

> 原文:[https://www . geesforgeks . org/class-islocalclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-islocalclass-method-in-java-with-examples/)

**[Java . lang . Class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **isLocalClass()** 方法用于检查该类是否为 Local 类。如果此类是本地类，则方法返回 true。否则返回 false。

**语法:**

```
public boolean isLocalClass()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是本地类，这个方法返回**真**。否则返回**假**。

下面的程序演示了 isLocalClass()方法。

**例 1:**

```
// Java program to demonstrate isLocalClass() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an localClass
        // using isLocalClass() method
        System.out.println("Is Test an localClass: "
                           + myClass.isLocalClass());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Is Test an localClass: false

```

**例 2:**

```
// Java program to demonstrate isLocalClass() method

public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        class A {
        }

        // returns the Class object for A
        Class myClass = A.class;

        // Check if myClass is an localClass
        // using isLocalClass() method
        System.out.println("Is A an localClass: "
                           + myClass.isLocalClass());
    }
}
```

**输出:**

```
Is A an localClass: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # isLocalClass–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isLocalClass--)