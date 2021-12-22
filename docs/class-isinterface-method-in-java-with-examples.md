# 用示例在 Java 中类 isInterface()方法

> 原文:[https://www . geesforgeks . org/class-is interface-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-isinterface-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **isInterface()** 方法用于检查该类是否为接口。如果此类是接口，则方法返回 true。否则返回 false。

**语法:**

```java
public boolean isInterface()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是接口，这个方法返回**真**。否则返回**假**。

下面的程序演示了 isInterface()方法。

**例 1:**

```java
// Java program to demonstrate isInterface() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an interface
        // using isInterface() method
        System.out.println("Is Test an interface: "
                           + myClass.isInterface());
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Is Test an interface: false

```

**例 2:**

```java
// Java program to demonstrate isInterface() method

interface T {
}

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("T");

        // Check if T is an interface
        // using isInterface() method
        System.out.println("Is T an interface: "
                           + myClass.isInterface());
    }
}
```

**输出:**

```java
Is T an interface: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # Isinterface–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isInterface--)