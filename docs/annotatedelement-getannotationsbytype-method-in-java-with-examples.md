# 用示例注释 Java 中的 getAnnotationsByType()方法

> 原文:[https://www . geeksforgeeks . org/annotatedelement-getannotationsbytype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/annotatedelement-getannotationsbytype-method-in-java-with-examples/)

**Java . lang . annotatedeleement 类**的 **getAnnotationsByType()** 方法用于获取实现该接口的类中存在的指定注释类型的注释。方法返回指定批注类型的批注数组。

**语法:**

```
public A[] getAnnotationsByType(Class<T> annotationClass)

```

**参数:**该方法接受一个参数**标注类**，即要获取的标注类型。

**返回值:**该方法返回**指定标注类型的标注数组**。

**异常:**此方法抛出:

*   **NullPointRexception:**如果给定的注释类为空。

下面的程序演示了 getAnnotationsByType()方法。

**例 1:**

```
// Java program to demonstrate
// getAnnotationsByType() method

import java.util.*;
import java.lang.reflect.*;
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

        // returns the Class object
        // for this myAnnotatedElement
        AnnotatedElement myAnnotatedElement
            = Test.class;

        System.out.println(
            "AnnotatedElement represented"
            + " by myAnnotatedElement: "
            + myAnnotatedElement.toString());

        // Get the annotation
        // using getAnnotationsByType() method
        System.out.println(
            "Annotation of myAnnotatedElement"
            + " of type Annotation: "
            + Arrays.toString(
                  myAnnotatedElement
                      .getAnnotationsByType(
                          Annotation.class)));
    }
}
```

**Output:**

> 用 my annotationdelete 表示的注释标注:类测试
> 类型的 my annotationdelete 的注释标注:[@Annotation(key=GFG，value=GeeksForGeeks)]

**例 2:**

```
// Java program to demonstrate
// getAnnotationsByType() method

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

            // Get the annotation
            // using getAnnotationsByType() method
            System.out.println(
                "Annotation of myAnnotatedElement"
                + " of type Deprecated: "
                + Arrays.toString(
                      myAnnotatedElement
                          .getAnnotationsByType(
                              Deprecated.class)));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

> 由 my announatedelement 表示的批注:类测试
> 类型的 my announatedelement 的批注已弃用:[@java.lang .弃用()]

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/reflect/annotatedelement . html # getAnnotationsByType-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#getAnnotationsByType-java.lang.Class-)