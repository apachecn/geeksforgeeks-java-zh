# Java –@目标注释

> 原文:[https://www.geeksforgeeks.org/java-targeted-annotations/](https://www.geeksforgeeks.org/java-targeted-annotations/)

[Java 中的注释](https://www.geeksforgeeks.org/annotations-in-java/)用于将元数据与类、方法、实例变量等程序元素相关联。java 中的注释主要有三种类型:标记注释(不带任何方法)、单值注释(带单个方法)和多值注释(带多个方法)。@Target 批注是元批注，即只能用于批注其他批注。它将 ElementType 枚举作为唯一的参数。ElementType 枚举是一个常量，它指定程序元素声明的类型(类、接口、构造函数等)。)可以应用注释。如果我们将带有某些元素类型的@Target 注释作为注释应用于自定义注释名称 custom annotation，那么@CustomAnnotation 只能用于注释那些特定的元素类型，否则我们将会得到一个错误。

下表显示了元素类型，可以注释的元素声明如下:

<figure class="table">T26】局部 _ 变量 T32】注释 _ 类型

| 元素类型 | 要注释的元素 |
| --- | --- |
| 类型 | 类、接口或枚举 |
| 字段 | 字段 |
| 方法 | 方法 |
| 构造函数 | 构造函数 |
| 局部变量 |

</figure>

为了使用@Target 注释，请遵循以下语法:

**语法:**

```
@Target(ElementType.TYPE)
@interface CustomAnnotation {}
```

在上面提到的代码示例中，我们创建了一个使用@Target 注释的自定义注释。由于我们已经使用了元素类型作为类型，因此，自定义注释只能注释一个类、枚举或接口。我们还可以通过给@Target 注释一个大括号分隔的元素类型列表作为参数，来创建一个可以应用于多个元素的自定义注释，如下所示。

**语法:**

```
@Target({ElementType.METHOD, ElementType.PACKAGE})
@interface CustomAnnotation {}
```

上面创建的自定义注释可用于注释方法或包。下面提到的代码展示了我们如何使用@Target 注释。我们已经创建了两个自定义注释:一个可以应用于单个元素类型，一个可以应用于多个元素类型。然后我们将这些注释应用于我们的类和方法，最后，我们通过获取它们来打印这些注释。

**实施:**

**示例**

## Java

```
// Java program to Illustrate Targeted Annotations

// Importing required classes from java.lang package 
import java.lang.annotation.*;

// Creating a custom annotation with target
// as TYPE which means it can annotate a class,
// enumeration, or interface
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)

// Class Annotation
@interface ClassAnnotation
{
    String value() default "Can annotate a class";
}

// Creating custom annotation with
// target as multiple Element types as parameters
// which means it can annotate various Elements
@Target({ ElementType.METHOD, ElementType.TYPE,
          ElementType.ANNOTATION_TYPE,
          ElementType.CONSTRUCTOR })
@Retention(RetentionPolicy.RUNTIME)
@interface MultipleElementTypeAnnotation
{

    String value() default "Can annotate a class, method, "
        + "annotation, or constructor";
}

// Class to demonstrate the use of custom
// created annotations
@ClassAnnotation

// Main class
// TargetAnnotationDemo
public class GFG {

    @MultipleElementTypeAnnotation public void myMethod() {}

    // Main drive method
    public static void main(String[] args) throws Exception
    {
        GFG obj = new GFG();

        // Accessing the annotations used to annotate the
        // class and storing them in an array of Annotation
        // type since only one annotation is used to
        // annotate our class therefore we print a[0]
        Annotation a[] = obj.getClass().getAnnotations();

        System.out.println(a[0]);

        // Accessing the annotations used to annotate the
        // method and storing them in an array of Annotation
        // type
        Class<?> className = Class.forName("GFG");
        Annotation b[] = className.getMethod("myMethod")
                             .getAnnotations();

        System.out.println(b[0]);
    }
}
```

**输出**

```
@ClassAnnotation(value="Can annotate a class")
@MultipleElementTypeAnnotation(value="Can annotate a class, method, annotation, or constructor")
```