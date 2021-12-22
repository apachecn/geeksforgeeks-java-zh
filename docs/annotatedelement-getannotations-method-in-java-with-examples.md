# 用示例注释 Java 中的 getAnnotations()方法

> 原文:[https://www . geeksforgeeks . org/annatedelement-getannotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/annotatedelement-getannotations-method-in-java-with-examples/)

**Java . lang . annotatedeleement 类**的 **getAnnotations()** 方法用于获取实现该接口的类中存在的注释。方法返回存在的注释数组。

**语法:**

```
public Annotation[] getAnnotations()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**一组存在的注释**。

下面的程序演示了 getAnnotations()方法。

**例 1:**

```
// Java program to demonstrate
// getAnnotations() method

import java.lang.reflect.*;
import java.util.*;
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
            // using getAnnotations() method
            System.out.println(
                "Annotation of myAnnotatedElement: "
                + Arrays.toString(
                      myAnnotatedElement
                          .getAnnotations()));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

> 由 my annotationdelete:class Test 表示的批注 my annotationdelete:[@ Java . lang .弃用()]的
> 批注

**例 2:**

```
// Java program to demonstrate
// getAnnotations() method

import java.lang.reflect.*;
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

        // returns the Class object
        // for this myAnnotatedElement
        AnnotatedElement myAnnotatedElement
            = Test.class;

        System.out.println(
            "AnnotatedElement represented"
            + " by myAnnotatedElement: "
            + myAnnotatedElement.toString());

        // Get the annotation
        // using getAnnotations() method
        System.out.println(
            "Annotation of myAnnotatedElement: "
            + Arrays.toString(
                  myAnnotatedElement
                      .getAnnotations()));
    }
}
```

**Output:**

> 用 my annotationdelete 表示的注解:类测试
> my annotationdelete 的注解:[@Annotation(键=GFG，值=GeeksForGeeks)]

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/reflect/annotatedelement . html # getAnnotations–](https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#getAnnotations--)