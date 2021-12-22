# Java 中的类 getAnnotation()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getannotation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getannotation-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getAnnotation()** 方法用于获取指定注释类型的注释，如果该类中存在这样的注释。方法以对象的形式返回该类。

**语法:**

```java
public T getAnnotation(Class<T> annotationClass)

```

**参数:**该方法接受一个参数**标注类**，即要获取的标注类型。

**返回值:**该方法返回标注类的指定**对象**。

**异常:**如果给定的注释类为空，该方法抛出:

*   **[null pointer exception:** .

下面的程序演示了 getAnnotation()方法。

**例 1:**

```java
// Java program to demonstrate
// getAnnotation() method

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

        // Get the annotation
        // using getAnnotation() method
        System.out.println(
            "Annotation of myClass: "
            + myClass.getAnnotation(
                  Annotation.class));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Annotation of myClass: @Annotation(key=GFG, value=GeeksForGeeks)

```

**例 2:**

```java
// Java program to demonstrate
// getAnnotation() method

import java.util.*;
import java.lang.annotation.*;

// Class with no annotations
// getAnnotation() will return null
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the annotation
        // using getAnnotation() method
        System.out.println(
            "Annotation of myClass: "
            + myClass.getAnnotation(
                  Annotation.class));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Annotation of myClass: null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getAnnotation-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getAnnotation-java.lang.Class-)