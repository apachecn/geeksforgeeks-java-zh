# Java 中的类 getPackageName()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getpackagename-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getpackagename-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getPackageName()** 方法用于获取该实体的包名。这个实体可以是类、数组、接口等。方法以字符串形式返回此实体的包名。

**语法:**

```java
public String getPackageName()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法将该实体的**包名**作为字符串返回。

下面的程序演示了 getPackageName()方法。

**注意:**这个方法是 Java 9 中引入的。因此，要运行这个方法，我们需要一个 Java 9 编译器。所以这不会在在线 IDE 中运行。

**例 1:**

```java
// Java program to demonstrate getPackageName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the package name of myClass
        // using getPackageName() method
        System.out.println("PackageName of myClass: "
                           + myClass.getPackageName());
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
PackageName of myClass: 

```

**例 2:**

```java
// Java program to demonstrate getPackageName() method

public class Test {

    class Arr {
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object
        Class myClass = Class.forName("java.lang.String");

        // Get the package name of myClass
        // using getPackageName() method
        System.out.println("PackageName of myClass: "
                           + myClass.getPackageName());
    }
}
```

**输出:**

```java
Class represented by myClass: class java.lang.String
PackageName of myClass: java.lang

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getPackageName–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getPackageName--)