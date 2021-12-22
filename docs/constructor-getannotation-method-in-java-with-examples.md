# Java 中的构造函数 getAnnotation()方法，示例

> 原文:[https://www . geeksforgeeks . org/constructor-getannotation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getannotation-method-in-java-with-examples/)

**构造函数**类的 **getAnnotation()** 方法用于获取指定类型的构造函数对象注释，如果存在这样的注释，则为空。指定的类型作为参数传递。

**语法:**

```java
public <T extends Annotation> T
  getAnnotation(Class<T> annotationClass)

```

**参数:**该方法接受单个参数**标注类**，表示标注类型对应的类对象。

**返回值:**该方法返回指定标注类型的**该元素的标注**(如果存在于该元素中，否则为空)。

**异常:**如果给定的注释类为空，该方法抛出**空指针异常**。

下面的程序说明了 getAnnotation()方法:
**程序 1:**

```java
// Java program to demonstrate
// Constructor.getAnnotation() method

import java.lang.annotation.Annotation;
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String... args)
        throws NoSuchMethodException
    {

        // Create Constructor Object
        Constructor[] constructors
            = Demo.class.getConstructors();

        // Create annotation object
        Annotation annotation
            = constructors[0]
                  .getAnnotation(PathVar.class);

        if (annotation instanceof PathVar) {

            PathVar customAnnotation
                = (PathVar)annotation;
            System.out.println(
                "Path: "
                + customAnnotation.Path());
        }
    }
}

// Demo class
class Demo {
    public Demo(@PathVar(Path = "Demo/usr")
                String str) {}
}

// PathVar interface
@Target({ ElementType.TYPE_USE })
@Retention(RetentionPolicy.RUNTIME)
@interface PathVar {
    public String Path();
}
```

**输出:**

```java
Path: Demo/usr

```

**程序 2:**

```java
// Java program to demonstrate
// Constructor.getAnnotation() method

import java.lang.annotation.Annotation;
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String... args)
        throws NoSuchMethodException
    {

        // Create Constructor Object
        Constructor[] constructors
            = Maths.class.getConstructors();

        // Create annotation object
        Annotation annotation
            = constructors[0]
                  .getAnnotation(Calculator.class);

        System.out.println(
            "Annotation:"
            + annotation.toString());
    }
}

// Demo class
@Calculator(add = "Adding value",
            subtract = "Subtracting Value")
class Maths {

    @Calculator(add = "Adding value",
                subtract = "Subtracting Value")
    public Maths() {}
}

// Calculator interface
@Retention(RetentionPolicy.RUNTIME)
@interface Calculator {
    public String add();
    public String subtract();
}
```

**输出:**

```java
Annotation : @Calculator(add=Adding value, subtract=Subtracting Value)

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getAnnotation(Java . lang . class)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getAnnotation(java.lang.Class))