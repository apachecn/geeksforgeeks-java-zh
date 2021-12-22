# 用示例在 Java 中类 getPackage()方法

> 原文:[https://www . geesforgeks . org/class-getpackage-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getpackage-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getPackage()** 方法用于获取该实体的包。这个实体可以是类、数组、接口等。方法返回该实体的包。

**语法:**

```
public Package getPackage()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该实体的**包**。

下面的程序演示了 getPackage()方法。

**例 1:**

```
// Java program to demonstrate getPackage() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the Package of myClass
        // using getPackage() method
        System.out.println("Package of myClass: "
                           + myClass.getPackage());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Package of myClass: null

```

**例 2:**

```
// Java program to demonstrate getPackage() method

public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object
        Class myClass = Class.forName("java.lang.String");

        // Get the package of myClass
        // using getPackage() method
        System.out.println("Package of myClass: "
                           + myClass.getPackage());
    }
}
```

**输出:**

```
Package of myClass: package java.lang,
 Java Platform API Specification,
 version 1.8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getPackage–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getPackage--)