# Java 中的 Class isInstance()方法，示例

> 原文:[https://www . geesforgeks . org/class-is instance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-isinstance-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **isInstance()** 方法用于检查指定的对象是否兼容，以分配给该类的实例。如果指定的对象为非空，并且可以转换为此类的实例，则方法返回 true。否则返回 false。

**语法:**

```java
public boolean isInstance(Object object)

```

**参数:**该方法接受**对象**作为参数，该参数是要检查与该类实例兼容性的指定对象。

**返回值:**如果指定的对象为非空，并且可以转换为此类的实例，则此方法返回 **true** 。否则返回**假**。

下面的程序演示了 isInstance()方法。

**例 1:**

```java
// Java program to demonstrate isInstance() method

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
        // using isInstance() method
        System.out.println("Is c compatible: "
                           + myClass.isInstance(c));
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
// Java program to demonstrate isInstance() method

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
        // using isInstance() method
        System.out.println("Is c compatible: "
                           + myClass.isInstance(c));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Class represented by c: class Test
Is c compatible: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # is instance-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isInstance-java.lang.Object-)