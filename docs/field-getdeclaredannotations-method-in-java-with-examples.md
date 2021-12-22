# Java 中的 Field getDeclaredAnnotations()方法示例

> 原文:[https://www . geesforgeks . org/field-getdeclaredannotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getdeclaredannotations-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getDeclaredAnnotations()** 方法用于返回直接出现在此 Field 对象上的注释，并忽略继承的注释。如果此元素上没有直接存在的注释，则返回值为空数组。调用方可以在方法发送实际对象的副本时修改返回的数组；它对返回给其他调用方的数组没有影响。

**语法:**

```
public Annotation[] getDeclaredAnnotations()

```

**参数:**此方法不接受任何东西。

**返回**:该方法返回直接出现在该元素上的**注释**。

下面的程序说明了 getDeclaredAnnotations()方法:
**程序 1:**

```
// Java program to illustrate
// getDeclaredAnnotations() method

import java.lang.annotation.*;
import java.lang.reflect.Field;
import java.util.Arrays;

public class GFG {

    // initialize field with  annotation
    private int @SpecialNumber[] number;

    public static void main(String[] args)
        throws NoSuchFieldException
    {
        // get Field object
        Field field
            = GFG.class.getDeclaredField("number");

        // apply getAnnotatedType() method
        Annotation[] annotations
            = field.getDeclaredAnnotations();

        // print the results
        System.out.println(
            Arrays
                .toString(annotations));
    }

    @Target({ ElementType.TYPE_USE })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface SpecialNumber {
    }
}
```

**Output:**

```
[]

```

**程序 2:**

```
// Java program to illustrate
// getDeclaredAnnotations() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Field;
import java.util.Arrays;

public class GFG {

    // initialize field with  annotation
    @Deprecated
    private String string
        = " Welcome to GeeksForGeeks";

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // create Field object
        Field field
            = GFG.class
                  .getDeclaredField("string");

        // apply getAnnotation()
        Annotation[] annotations
            = field.getDeclaredAnnotations();

        // print results
        System.out.println(
            Arrays
                .toString(annotations));
    }
}
```

**Output:**

```
[@java.lang.Deprecated()]

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getDeclaredAnnotations–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getDeclaredAnnotations--)