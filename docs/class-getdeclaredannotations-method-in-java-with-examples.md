# Java 中的类 getDeclaredAnnotations()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredannotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredannotations-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getDeclaredAnnotations()** 方法用于获取该类中存在的已声明的注释。方法返回一个已声明注释的数组。

**语法:**

```java
public DeclaredAnnotation[] getDeclaredAnnotations()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回**一个声明注释的数组**存在。

下面的程序演示了 getDeclaredAnnotations()方法。

**例 1:**

```java
// Java program to demonstrate
// getDeclaredAnnotations() method

import java.util.*;
import java.lang.annotation.*;

@Deprecated
public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        try {
            // returns the Class object for this class
            Class myClass = Test.class;

            System.out.println(
                "Class represented by myClass: "
                + myClass.toString());

            // Get the declared annotation
            // using getDeclaredAnnotations() method
            System.out.println(
                "DeclaredAnnotation of myClass: "
                + Arrays.toString(
                      myClass.getDeclaredAnnotations()));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
DeclaredAnnotation of myClass: [@java.lang.Deprecated()]

```

**例 2:**

```java
// Java program to demonstrate
// getDeclaredAnnotations() method

import java.util.*;
import java.lang.annotation.*;

// create a custom DeclaredAnnotation
@Retention(RetentionPolicy.RUNTIME)
@interface DeclaredAnnotation {

    // This declared annotation has two attributes.
    public String key();

    public String value();
}

// call DeclaredAnnotation for method
// and pass values for declared annotation
@DeclaredAnnotation(key = "GFG", value = "GeeksForGeeks")
public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println(
            "Class represented by myClass: "
            + myClass.toString());

        // Get the declared annotation
        // using getDeclaredAnnotations() method
        System.out.println(
            "DeclaredAnnotation of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredAnnotations()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
DeclaredAnnotation of myClass: [@DeclaredAnnotation(key=GFG, value=GeeksForGeeks)]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getdeclarredannotations–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredAnnotations--)