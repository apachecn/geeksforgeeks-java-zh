# Java 中的类 toString()方法，示例

> 原文:[https://www . geesforgeks . org/class-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-tostring-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **toString()** 方法用于将该类的实例转换为字符串表示形式。此方法返回形成的字符串表示形式。

**语法:**

```
public String toString()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个对象的字符串表示。

下面的程序演示了 toString()方法。

**例 1:**

```
// Java program to demonstrate toString() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        System.out.print("Class represented by c1: ");

        // toString method on c1
        System.out.println(c1.toString());
    }
}
```

**输出:**

```
Class represented by c1: class java.lang.String

```

**例 2:**

```
// Java program to demonstrate toString() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c2 = int.class;
        Class c3 = void.class;

        System.out.print("Class represented by c2: ");

        // toString method on c2
        System.out.println(c2.toString());

        System.out.print("Class represented by c3: ");

        // toString method on c3
        System.out.println(c3.toString());
    }
}
```

**输出:**

```
Class represented by c2: int
Class represented by c3: void

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#toString--)