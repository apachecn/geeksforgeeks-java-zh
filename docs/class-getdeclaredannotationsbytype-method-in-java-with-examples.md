# Java 中的类 getDeclaredAnnotationsByType()方法，示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredannotationbytype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredannotationsbytype-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的**getdeclaredannotationbytype()**方法用于获取该类中存在的指定声明注释类型的声明注释。方法返回指定声明注释类型的声明注释数组。

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
        // using getDeclaredAnnotationsByType() method
        System.out.println(
            "DeclaredAnnotation of myClass of type DeclaredAnnotation: "
            + Arrays.toString(
                  myClass
                      .getDeclaredAnnotationsByType(
                          DeclaredAnnotation.class)));
    }
}
```

****输出:****

> **由 myClass 表示的类:class Test
> DeclaredAnnotation 类型的 myClass 的 DeclaredAnnotation:[@ DeclaredAnnotation(key = GFG，value=GeeksForGeeks)]**

****例 2:****

```java
// Java program to demonstrate
// getDeclaredAnnotationsByType() method

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
            // using getDeclaredAnnotationsByType() method
            System.out.println(
                "DeclaredAnnotation of myClass of type Deprecated: "
                + Arrays.toString(
                      myClass
                          .getDeclaredAnnotationsByType(
                              Deprecated.class)));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****输出:****

> **由 myClass 表示的类:class Test
> DeclaredAnnotation 类型的 myClass 已弃用:[@java.lang.Deprecated()]**

****参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getdeclaredannotationbytype-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredAnnotationsByType-java.lang.Class-)**