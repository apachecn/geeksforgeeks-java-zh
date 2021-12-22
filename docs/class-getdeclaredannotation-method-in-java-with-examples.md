# Java 中的类 getDeclaredAnnotation()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredannotation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredannotation-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getDeclaredAnnotation()** 方法用于获取指定声明注释类型的声明注释，如果该类中存在这样的声明注释。方法以对象的形式返回该类。

**语法:**

```java
public T getDeclaredAnnotation(Class<T> declared annotationClass)

```

**参数:**该方法接受一个参数**声明的注释类**，它是要获取的声明注释的类型。

**返回值:**该方法返回声明的标注类的指定**对象**。

**异常:**此方法抛出:

*   **NullPointRexception:**如果给定的声明注释类为空。

下面的程序演示了 getDeclaredAnnotation()方法。

**例 1:**

```java
// Java program to demonstrate
// getDeclaredAnnotation() method

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
        // using getDeclaredAnnotation() method
        System.out.println(
            "DeclaredAnnotation of myClass: "
            + myClass
                  .getDeclaredAnnotation(
                      DeclaredAnnotation.class));
    }
}
```

**输出:**

> 由 myClass 表示的类:class Test
> DeclaredAnnotation of my class:@ DeclaredAnnotation(键=GFG，值=GeeksForGeeks)

**例 2:**

```java
// Java program to demonstrate
// getDeclaredAnnotation() method

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
            // using getDeclaredAnnotation() method
            System.out.println(
                "DeclaredAnnotation of myClass: "
                + myClass
                      .getDeclaredAnnotation(
                          Deprecated.class));
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
DeclaredAnnotation of myClass: @java.lang.Deprecated()

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getdeclarredannotation-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredAnnotation-java.lang.Class-)