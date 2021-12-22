# Java 中的类 isEnum()方法，带示例

> 原文:[https://www . geesforgeks . org/class-isenum-in-Java-method-with-examples/](https://www.geeksforgeeks.org/class-isenum-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **isEnum()** 方法用于检查该类是否是枚举类。如果此类是枚举类，则方法返回 true。否则返回 false。

**语法:**

```java
public boolean isEnum()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是枚举类，这个方法返回**真**。否则返回**假**。

下面的程序演示了 isEnum()方法。

**例 1:**

```java
// Java program to demonstrate isEnum() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an enum
        // using isEnum() method
        System.out.println("Is Test an enum: "
                           + myClass.isEnum());
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Is Test an enum: false

```

**例 2:**

```java
// Java program to demonstrate isEnum() method

enum A {}

public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for A
        Class myClass = A.class;

        // Check if myClass is an enum
        // using isEnum() method
        System.out.println("Is A an enum: "
                           + myClass.isEnum());
    }
}
```

**输出:**

```java
Is A an enum: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # isEnum–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isEnum--)