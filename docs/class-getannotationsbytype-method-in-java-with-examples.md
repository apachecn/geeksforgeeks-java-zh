# Java 中的类 getAnnotationsByType()方法，带示例

> 原文:[https://www . geeksforgeeks . org/class-getannotationsbytype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getannotationsbytype-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getAnnotationsByType()** 方法用于获取该类中存在的指定标注类型的标注。方法返回指定批注类型的批注数组。

**语法:**

```java
public A[] getAnnotationsByType(Class<T> annotationClass)

```

**参数:**该方法接受一个参数**标注类**，即要获取的标注类型。

**返回值:**该方法返回**指定标注类型的标注数组**。

**异常:**如果给定的注释类为空，该方法抛出:

*   **[null pointer exception:** .

下面的程序演示了 getAnnotationsByType()方法。

**例 1:**

```java
// Java program to demonstrate
// getAnnotationsByType() method

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

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println(
            "Class represented by myClass: "
            + myClass.toString());

        // Get the annotation
        // using getAnnotationsByType() method
        System.out.println(
            "Annotation of myClass of type Annotation: "
            + Arrays.toString(
                  myClass
                      .getAnnotationsByType(
                          Annotation.class)));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
Annotation of myClass of type Annotation: [@Annotation(key=GFG, value=GeeksForGeeks)]

```

**例 2:**

```java
// Java program to demonstrate
// getAnnotationsByType() method

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

            // Get the annotation
            // using getAnnotationsByType() method
            System.out.println(
                "Annotation of myClass of type Deprecated: "
                + Arrays.toString(
                      myClass
                          .getAnnotationsByType(
                              Deprecated.class)));
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
Annotation of myClass of type Deprecated: [@java.lang.Deprecated()]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getannocationsbytype-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getAnnotationsByType-java.lang.Class-)