# Java 中构造函数 getParameterAnnotations()方法，示例

> 原文:[https://www . geesforgeks . org/constructor-get parameter annotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getparameterannotations-method-in-java-with-examples/)

一个**构造函数**类的**getparameter annotations()**方法用于获取一个二维的 Annotation 数组，该数组表示该构造函数的形式参数上的注释。如果构造函数不包含参数，将返回一个空数组。如果构造函数包含一个或多个参数，那么将返回一个二维注释数组。对于没有注释的参数，此二维数组的嵌套数组将为空。此方法返回的注释对象是可序列化的。此方法返回的数组可以很容易地修改。

**语法:**

```
public Annotation[][] getParameterAnnotations()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个**数组**，这个数组按照声明顺序表示这个对象表示的可执行文件的形式和隐式参数的注释。

下面的程序说明了 getParameterAnnotations()方法:
**程序 1:**

```
// Java program to demonstrate
// Constructor.getParameterAnnotations() method

import java.lang.annotation.Annotation;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Constructor;
import java.util.Arrays;

public class GFG {

    public static void main(String... args)
        throws NoSuchMethodException
    {

        // Create Constructor Object
        Constructor[] constructors
            = Test.class.getConstructors();

        // get Annotation array
        Annotation[][] annotations
            = constructors[0].getParameterAnnotations();

        System.out.println("Parameter annotations -->");
        System.out.println(Arrays.deepToString(annotations));
    }
}
class Test {

    public Test(@Properties Object config)
    {
    }
}

@Retention(RetentionPolicy.RUNTIME)
@interface Properties {
}
```

**输出:**

```
Parameter annotations -->
[[@Properties()]]

```

**程序 2:**

```
// Java program to demonstrate
// Constructor.getParameterAnnotations() method

import java.lang.annotation.Annotation;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String... args)
        throws NoSuchMethodException
    {

        // Create Constructor Object
        Constructor[] constructors
            = GfgDemo.class.getConstructors();

        // get Annotation array
        Annotation[][] annotations
            = constructors[0].getParameterAnnotations();

        System.out.println("Parameter annotations -->");
        for (Annotation[] ann : annotations) {
            for (Annotation annotation : ann) {
                System.out.println(annotation);
            }
        }
    }
}
class GfgDemo {

    public GfgDemo(@Path Path path)
    {
    }
}

@Retention(RetentionPolicy.RUNTIME)
@interface Path {
}
```

**输出:**

```
Parameter annotations -->
@Path()

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getparameter annotations()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getParameterAnnotations())