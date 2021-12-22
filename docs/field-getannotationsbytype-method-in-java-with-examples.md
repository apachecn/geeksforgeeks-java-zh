# Java 中的字段 getAnnotationsByType()方法，带示例

> 原文:[https://www . geeksforgeeks . org/field-getannotationsbytype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getannotationsbytype-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getAnnotationsByType()** 方法用于返回与该字段元素关联的注释。这是获取字段对象注释的重要方法。如果没有与此字段元素相关联的注释，则返回空数组。调用方可以在方法发送实际对象的副本时修改返回的数组；它对返回给其他调用方的数组没有影响。

**语法:**

```
public <T extends Annotation> T[] 
  getAnnotationsByType(Class<T> annotationClass)

```

**参数:**该方法接受**标注类**，即标注类型对应的类对象。

**返回**:如果与该元素相关联，则该方法返回指定注释类型的该元素的所有**注释**，否则返回长度为零的数组。

**异常**:如果给定的注释类为空，该方法抛出**空指针异常**。

下面的程序说明了 getAnnotationsByType()方法:
**程序 1:**

```
// Java program to illustrate
// getAnnotationsByType() method

import java.lang.annotation.*;
import java.lang.reflect.Field;
import java.util.Arrays;

public class GFG {

    // initialize field with
    // default value in annotation
    @annotations(32512.21)
    private double realNumbers;

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // create Field object
        Field field
            = GFG.class
                  .getDeclaredField("realNumbers");

        // apply getAnnotationsByType()
        annotations[] annotations
            = field.getAnnotationsByType(
                annotations.class);

        // print results
        System.out.println(
            Arrays
                .toString(annotations));
    }

    @Target({ ElementType.FIELD })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface annotations {
        double value() default 99.9;
    }
}
```

**Output:**

```
[@GFG$annotations(value=32512.21)]

```

**程序 2:**

```
// Java program to illustrate
// getAnnotationsByType() method

import java.lang.annotation.*;
import java.lang.reflect.Field;
import java.util.Arrays;

public class GFG {

    // initialize field with
    // default value in annotation
    @annotations("ChipherCodes@#!")
    private double string;

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // create a Field object
        Field field
            = GFG.class
                  .getDeclaredField("string");

        // apply getAnnotationsByType()
        annotations[] annotations
            = field.getAnnotationsByType(
                annotations.class);

        // print results
        System.out.println(
            Arrays.toString(
                annotations));
    }

    @Target({ ElementType.FIELD })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface annotations {
        String value();
    }
}
```

**Output:**

```
[@GFG$annotations(value=ChipherCodes@#!)]

```

**参考文献:**T2