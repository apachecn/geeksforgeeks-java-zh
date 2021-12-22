# Java 中的 Field getAnnotatedType()方法，带示例

> 原文:[https://www . geeksforgeeks . org/field-getannotedtype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getannotatedtype-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getAnnotatedType()** 方法用于返回一个 annonatedType 对象，该对象表示使用一个类型来指定该字段的声明类型。该类的每个字段都由一些注释类型声明。AnnotatedType 表示任何类型的潜在注释使用，包括数组类型、参数化类型、类型变量或 Java Virtual Machine 中当前运行的通配符类型。返回的 AnnotatedType 实例可以是 AnnotatedType 本身的实现，也可以是其子接口之一的实现:AnnotatedArrayType、AnnotatedParameterizedType、AnnotatedTypeVariable、AnnotatedWildcardType。

**语法:**

```java
public AnnotatedType getAnnotatedType()

```

**参数:**此方法不接受任何东西。

**返回**:该方法返回一个**对象**，代表该字段所代表的字段的声明类型。

下面的程序举例说明了 getAnnotatedType()方法:
**程序 1:**

```java
// Java program to illustrate
// getAnnotatedType() method

import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Field;
import java.util.Arrays;

public class GFG {

    private int number;

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get Field object
        Field field
            = GFG.class
                  .getDeclaredField("number");

        // apply getAnnotatedType() method
        AnnotatedType annotatedType
            = field.getAnnotatedType();

        // print the results
        System.out.println(
            "Type: "
            + annotatedType
                  .getType()
                  .getTypeName());
        System.out.println(
            "Annotations: "
            + Arrays
                  .toString(
                      annotatedType
                          .getAnnotations()));
    }
}
```

**Output:**

```java
Type: int
Annotations: []

```

**程序 2:**

```java
// Java Program to illustrate
// getAnnotatedType() method

import java.lang.annotation.*;
import java.lang.reflect.*;
import java.util.Arrays;

public class GFG {

    private int @SpecialNumber[] number;

    public static void main(String[] args)
        throws NoSuchFieldException
    {
        // get Field object
        Field field
            = GFG.class
                  .getDeclaredField("number");

        // apply getAnnotatedType() method
        AnnotatedType annotatedType
            = field.getAnnotatedType();

        // print the results
        System.out.println(
            "Type: "
            + annotatedType
                  .getType()
                  .getTypeName());
        System.out.println(
            "Annotations: "
            + Arrays
                  .toString(
                      annotatedType
                          .getAnnotations()));
        System.out.println(
            "Declared Annotations: "
            + Arrays
                  .toString(
                      annotatedType
                          .getDeclaredAnnotations()));
    }

    @Target({ ElementType.TYPE_USE })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface SpecialNumber {
    }
}
```

**Output:**

```java
Type: int[]
Annotations: [@GFG$SpecialNumber()]
Declared Annotations: [@GFG$SpecialNumber()]

```

**参考文献:**T2