# Java 中的类 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/class-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-hashcode-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **hashCode()** 方法用来获取这个实体的 hashCode 表示。此方法返回一个整数值，即哈希码。

**语法:**

```
public int hashCode()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**整数值**，它是 hashCode。

下面的程序演示了 hashCode()方法。

**例 1:**

```
// Java program to demonstrate hashCode() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        System.out.println("Class represented by c1: "
                         + c1);

        // hashCode method on c1
        System.out.println("HashCode value: "
                           + c1.hashCode());
    }
}
```

**输出:**

```
Class represented by c1: class java.lang.String
HashCode value: 589431969

```

**例 2:**

```
// Java program to demonstrate hashCode() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = int.class;

        System.out.println("Class represented by c1: "
                         + c1);

        // hashCode method on c1
        System.out.println("HashCode value: "
                           + c1.hashCode());
    }
}
```

**输出:**

```
Class represented by c1: int
HashCode value: 589431969

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#hashCode--)