# Java 中的 annotatedelete getDeclaredAnnotations()方法，带示例

> 原文:[https://www . geeksforgeeks . org/annotatedelement-getdeclaredannotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/annotatedelement-getdeclaredannotations-method-in-java-with-examples/)

**Java . lang . annotatedeleement 类**的 **getDeclaredAnnotations()** 方法用于获取实现该接口的类中存在的已声明的注释。方法返回一个已声明注释的数组。

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
import java.lang.reflect.*;
import java.lang.annotation.*;

@Deprecated
public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        try {

            // returns the Class object
            // for this myAnnotatedElement
            AnnotatedElement myAnnotatedElement
                = Test.class;

            System.out.println(
                "AnnotatedElement represented"
                + " by myAnnotatedElement: "
                + myAnnotatedElement.toString());

            // Get the declared annotation
            // using getDeclaredAnnotations() method
            System.out.println(
                "DeclaredAnnotation of myAnnotatedElement: "
                + Arrays.toString(
                      myAnnotatedElement
                          .getDeclaredAnnotations()));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

> 由 my announatedelement 表示的批注:类测试
> 声明 my announatedelement 的批注:[@java.lang .弃用()]

**例 2:**

```java
// Java program to demonstrate
// getDeclaredAnnotations() method

import java.util.*;
import java.lang.reflect.*;
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

        // returns the Class object
        // for this myAnnotatedElement
        AnnotatedElement myAnnotatedElement
            = Test.class;

        System.out.println(
            "AnnotatedElement represented"
            + " by myAnnotatedElement: "
            + myAnnotatedElement.toString());

        // Get the declared annotation
        // using getDeclaredAnnotations() method
        System.out.println(
            "DeclaredAnnotation of myAnnotatedElement: "
            + Arrays.toString(
                  myAnnotatedElement
                      .getDeclaredAnnotations()));
    }
}
```

**Output:**

> 由 my annotationdelete 表示的注释注释:类测试
> 声明 my annotationdelete 的注释:[@ declarredannotation(key = GFG，value=GeeksForGeeks)]

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/reflect/annotatedelement . html # getDeclaredAnnotations–](https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#getDeclaredAnnotations--)