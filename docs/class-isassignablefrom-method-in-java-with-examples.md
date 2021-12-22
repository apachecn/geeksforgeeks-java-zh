# Java 中的 Class isAssignableFrom()方法，示例

> 原文:[https://www . geesforgeks . org/class-isassignablefrom-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-isassignablefrom-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **isAssignableFrom()** 方法用于检查指定类的对象是否兼容，以分配给该类的实例。如果两个类相同，或者指定的类是超类或超接口，它将是兼容的。如果指定类的对象可以转换为此类的实例，则方法返回 true。否则返回 false。

**语法:**

```java
public boolean isAssignableFrom(Class<T> class)

```

**参数:**该方法接受**类**作为参数，该参数是要检查其对象与该类实例的兼容性的指定类。

**返回值:**如果指定类的对象可以转换为该类的实例，则该方法返回 **true** 。否则返回**假**。

下面的程序演示了 isAssignableFrom()方法。

**例 1:**

```java
// Java program to demonstrate isAssignableFrom() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // get the Class instance using forName() method
        Class c = Class.forName("java.lang.String");

        System.out.println("Class represented by c: "
                           + c.toString());

        // Check if object c is compatible
        // using isAssignableFrom() method
        System.out.println("Is c compatible: "
                           + myClass.isAssignableFrom(c));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Class represented by c: class java.lang.String
Is c compatible: false

```

**例 2:**

```java
// Java program to demonstrate isAssignableFrom() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // get the Class instance using forName() method
        Class c = Class.forName("Test");

        System.out.println("Class represented by c: "
                           + c.toString());

        // Check if object c is compatible
        // using isAssignableFrom() method
        System.out.println("Is c compatible: "
                           + myClass.isAssignableFrom(c));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Class represented by c: class Test
Is c compatible: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # isAssignableFrom-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isAssignableFrom-java.lang.Class-)