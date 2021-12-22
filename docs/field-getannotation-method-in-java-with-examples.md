# Java 中的 Field getAnnotation()方法，带示例

> 原文:[https://www . geeksforgeeks . org/field-getannotation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getannotation-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getAnnotation()** 方法用于返回指定类型的字段对象，如果存在这样的注释，则返回空值。这是获取字段对象注释的重要方法。

**语法:**

```
public <T extends Annotation> T
  getAnnotation(Class<T> annotationClass)

```

**参数:**此方法**标注类**，是标注类型对应的类对象。

**返回**:该方法返回指定标注类型的该元素的**标注**(如果存在于该元素中，否则为空)。

**异常**:如果给定的注释类为空，该方法抛出**空指针异常**。

下面的程序说明了 getAnnotation()方法:
**程序 1:**

```
// Java program to illustrate
// getAnnotation() method

import java.lang.annotation.*;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Field;
import java.util.Arrays;

public class GFG {

    // initialize field with
    // default value in annotation
    @annotations(3125462345.32155365326)

    private double realNumbers;

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // create Field object
        Field field
            = GFG.class
                  .getDeclaredField("realNumbers");

        // apply getAnnotation()
        annotations annotations
            = field.getAnnotation(
                annotations.class);

        // print results
        System.out.println(annotations);
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
@GFG$annotations(value=3.1254623453215537E9)

```

**程序 2:**

```
// Java program to illustrate
// getAnnotation() method

import java.lang.annotation.*;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Field;
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

        // apply getAnnotation() method
        AnnotatedType annotatedType
            = field.getAnnotation();

        // print the results
        System.out.println(
            "Type: "
            + annotatedType.getType()
                  .getTypeName());
        System.out.println(
            "Annotations: "
            + Arrays.toString(
                  annotatedType
                      .getAnnotations()));
        System.out.println(
            "Declared Annotations: "
            + Arrays.toString(
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

```
@GFG$annotations(value=WelcomeTOGFG)

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getAnnotation–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getAnnotation--)