# Java @保留注释

> 原文:[https://www.geeksforgeeks.org/java-retention-annotations/](https://www.geeksforgeeks.org/java-retention-annotations/)

在 Java 中，注释用于将元数据附加到程序元素，如类、方法、实例等。一些注释用于注释其他注释。这些类型的注释被称为元注释。@Retention 也是一些保留策略附带的元注释。这些保留策略决定了何时丢弃注释。有三种类型的保留策略:SOURCE、CLASS 和 RUNTIME。

*   **保留政策。SOURCE:** 使用 SOURCE 保留策略注释的注释在运行时被丢弃。
*   **保留政策。类:**使用类保留策略注释的注释记录在。类文件，但在运行时被丢弃。类是 Java 中的默认保留策略。
*   **保留政策。运行时:**使用运行时保留策略注释的注释在运行时被保留，并且可以在运行时在我们的程序中访问。

**实施:**

在这里，我们将创建三个带有保留策略的自定义注释，如 SOURCE、CLASS 和 RUNTIME。这些自定义注释后来被用来注释三个类，即 A、B 和 c。在主方法中，我们检查注释是否在运行时附加到类上。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Retention Annotations

// Importing required classes from java.lang package
import java.lang.annotation.Annotation;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;

// Here we will be creating 3 annotations with
// RetentionPolicy as SOURCE, CLASS, & RUNTIME

// Retention Annotation 1
@Retention(RetentionPolicy.SOURCE)

// Interaface
@interface SourceRetention
{
    String value() default "Source Retention";
}

// Retention Annotation 2
@Retention(RetentionPolicy.CLASS)

// Interface
@interface ClassRetention
{
    String value() default "Class Retention";
}

// Retention Annotation 3
@Retention(RetentionPolicy.RUNTIME)

// Interface
@interface RuntimeRetention
{
    String value() default "Runtime Retention";
}

// Annotating classes A, B, and C
// with our custom annotations
@SourceRetention
class A {
}

@ClassRetention
class B {
}

@RuntimeRetention
class C {
};

// Main class
public class RetentionPolicyDemo {

    // Main driver method
    public static void main(String[] args)
    {

        // Obtaining the array of annotations used to
        // annotate class A, B, and C. Array a and b will be
        // empty as their annotation are attached before
        // runtime while array c will contain the
        // RuntimeRetention annotation as it was marked with
        // RUNTIME retention policy
        Annotation a[]
            = new A().getClass().getAnnotations();
        Annotation b[]
            = new B().getClass().getAnnotations();
        Annotation c[]
            = new C().getClass().getAnnotations();

        // Printing the number of retained annotations of
        // each class at runtime
        System.out.println(
            "Number of annotations attached to "
            + "class A at Runtime: " + a.length);

        System.out.println(
            "Number of annotations attached to "
            + "class B at Runtime: " + b.length);

        System.out.println(
            "Number of annotations attached to "
            + "class C at Runtime: " + c.length);

        // Since the class C is annotated with an annotation
        // which which has retention policy as runtime so it
        // can be accessed during runtime while annotations
        // of other two classes are discarded before runtime
        // so they can't be accessed
        System.out.println(
            "Annotation attached to class C: " + c[0]);
    }
}
```

**Output**

```java
Number of annotations attached to class A at Runtime: 0
Number of annotations attached to class B at Runtime: 0
Number of annotations attached to class C at Runtime: 1
Annotation attached to class C: @RuntimeRetention(value="Runtime Retention")
```