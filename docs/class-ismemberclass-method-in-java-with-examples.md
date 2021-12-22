# Class 是 Java 中的 MemberClass()方法，带有示例

> 原文:[https://www . geesforgeks . org/class-is memberclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-ismemberclass-method-in-java-with-examples/)

**是**的**方法检查这个类是否是成员类。如果此类是成员类，则方法返回 true。否则返回 false。**

**语法:**

```
public boolean isMemberClass()

```

**参数:**此方法不接受任何参数。

**返回值:**如果这个类是成员类，这个方法返回**真**。否则返回**假**。

下面的程序演示了 isMemberClass()方法。

**例 1:**

```
// Java program to demonstrate isMemberClass() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an memberClass
        // using isMemberClass() method
        System.out.println("Is Test an memberClass: "
                           + myClass.isMemberClass());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Is Test an memberClass: false

```

**例 2:**

```
// Java program to demonstrate isMemberClass() method

public class Test {

    class A {
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for A
        Class myClass = A.class;

        // Check if myClass is an memberClass
        // using isMemberClass() method
        System.out.println("Is A an memberClass: "
                           + myClass.isMemberClass());
    }
}
```

**输出:**

```
Is A an memberClass: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # is memberclass–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isMemberClass--)