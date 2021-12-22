# Java 中的 annotatedeletion getdeclaredannotationbytype()方法，带示例

> 原文:[https://www . geeksforgeeks . org/annotatedelement-getdeclaredannotationbytype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/annotatedelement-getdeclaredannotationsbytype-method-in-java-with-examples/)

**Java . lang . annotatedeleement 类**的 **getDeclaredAnnotations()** 方法用于获取实现该接口的类中存在的指定声明注释类型的声明注释。方法返回指定声明注释类型的声明注释数组。

**语法:**

```java
public A[] getDeclaredAnnotationsByType(Class<T> declared annotationClass)

```

**参数:**该方法接受一个参数**声明的注释类**，它是要获取的声明注释的类型。

**返回值:**这个方法为指定的声明注释类型返回一个声明注释的数组**。**

****异常:**此方法抛出:**

*   ****NullPointRexception:**如果给定的声明注释类为空。**

**下面的程序演示了 getDeclaredAnnotationsByType()方法。**

****例 1:****

```java
// Java program to demonstrate
// getDeclaredAnnotationsByType() method

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
        // using getDeclaredAnnotationsByType() method
        System.out.println(
            "DeclaredAnnotation of myAnnotatedElement"
            + " of type DeclaredAnnotation: "
            + Arrays.toString(
                  myAnnotatedElement
                      .getDeclaredAnnotationsByType(
                          DeclaredAnnotation.class)));
    }
}
```

****Output:**

> 由 my annotationdelete 表示的注释注释:类测试
> 声明类型为 DeclaredAnnotation 的 my annotationdelete 的注释:[@DeclaredAnnotation(键=GFG，值=GeeksForGeeks)]** 

****例 2:****

```java
// Java program to demonstrate
// getDeclaredAnnotationsByType() method

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
            // using getDeclaredAnnotationsByType() method
            System.out.println(
                "DeclaredAnnotation of myAnnotatedElement"
                + " of type Deprecated: "
                + Arrays.toString(
                      myAnnotatedElement
                          .getDeclaredAnnotationsByType(
                              Deprecated.class)));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****Output:**

> 由 my announatedelement 表示的批注:类测试
> 声明类型为的 my announatedelement 的批注已弃用:[@java.lang.Deprecated()]** 

****参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/reflect/annotatedelement . html # getAnnotationsByType-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#getAnnotationsByType-java.lang.Class-)**