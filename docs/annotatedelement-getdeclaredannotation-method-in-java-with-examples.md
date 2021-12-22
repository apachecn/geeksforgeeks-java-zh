# Java 中的 annotatedelete getDeclaredAnnotation()方法，带示例

> 原文:[https://www . geeksforgeeks . org/annotatedelement-getdeclaredannotation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/annotatedelement-getdeclaredannotation-method-in-java-with-examples/)

**Java . lang . reflect . annotatedeleement 接口**的 **getDeclaredAnnotation()** 方法用于获取指定声明注释类型的声明注释，如果实现该接口的类中存在这样的声明注释。方法以对象的形式返回该类。

**语法:**

```java
public T getDeclaredAnnotation(Class<T> declared annotationClass)

```

**参数:**该方法接受一个参数**声明的注释类**，它是要获取的声明注释的类型。

**返回值:**该方法返回实现该接口的已声明标注类的指定**对象**。

**异常:**此方法抛出:

*   **NullPointRexception:**如果给定的声明注释类为空。

下面的程序演示了 getDeclaredAnnotation()方法。

**例 1:**

```java
// Java program to demonstrate
// getDeclaredAnnotation() method

import java.util.*;
import java.lang.annotation.*;
import java.lang.reflect.*;

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
        // using getDeclaredAnnotation() method
        System.out.println(
            "DeclaredAnnotation of myAnnotatedElement: "
            + myAnnotatedElement
                  .getDeclaredAnnotation(
                      DeclaredAnnotation.class));
    }
}
```

**Output:**

> 由 my annotationdelete 表示的注释注释:类测试
> 声明 my annotationdelete 的注释:@DeclaredAnnotation(键=GFG，值=GeeksForGeeks)

**例 2:**

```java
// Java program to demonstrate
// getDeclaredAnnotation() method

import java.util.*;
import java.lang.annotation.*;
import java.lang.reflect.*;

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
            // using getDeclaredAnnotation() method
            System.out.println(
                "DeclaredAnnotation of myAnnotatedElement: "
                + myAnnotatedElement
                      .getDeclaredAnnotation(
                          Deprecated.class));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

> 由 my annotationdelete:class Test 表示的 AnnotatedElement】声明 my annotationdelete 的注释:@java.lang .弃用()

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/reflect/annotatedelement . html # getDeclaredAnnotation-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#getDeclaredAnnotation-java.lang.Class-)