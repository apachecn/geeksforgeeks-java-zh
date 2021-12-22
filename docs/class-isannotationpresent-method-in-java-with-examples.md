# 类是 Java 中的 notationPresent()方法，带有示例

> 原文:[https://www . geesforgeks . org/class-is notationpresent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-isannotationpresent-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的**is notationpresent()**方法用于检查该类中是否存在指定注释类型的注释。方法返回一个表示相同内容的布尔值。

**语法:**

```java
public boolean isAnnotationPresent(Class<T> annotationClass)

```

**参数:**该方法接受一个参数**标注类**，即要获取的标注类型。

**返回值:**该方法返回**布尔值**表示相同。

**异常:**如果给定的注释类为空，该方法抛出:

*   **[null pointer exception:** .

下面的程序演示了 isAnnotationPresent()方法。

**例 1:**

```java
// Java program to demonstrate
// isAnnotationPresent() method

import java.util.*;
import java.lang.annotation.*;

// create a custom Annotation
@Retention(RetentionPolicy.RUNTIME)
@interface Annotation {

    // This annotation has two attributes.
    public String key();

    public String value();
}

// call Annotation for method
// and pass values for annotation
@Annotation(key = "GFG", value = "GeeksForGeeks")
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if there is any annotation
        // using isAnnotationPresent() method
        System.out.println(
            "If there is any annotation in myClass: "
            + myClass.isAnnotationPresent(
                  Annotation.class));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
If there is any annotation in myClass: true

```

**例 2:**

```java
// Java program to demonstrate
// isAnnotationPresent() method

import java.util.*;
import java.lang.annotation.*;

// Class with no annotations
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the annotation
        // using isAnnotationPresent() method
        System.out.println(
            "If there is any annotation in myClass: "
            + myClass.isAnnotationPresent(
                  Annotation.class));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
If there is any annotation in myClass: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # is notationpresent-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isAnnotationPresent-java.lang.Class-)