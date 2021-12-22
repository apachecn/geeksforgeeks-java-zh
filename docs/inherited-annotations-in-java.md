# Java 中继承的注释

> 原文:[https://www . geesforgeks . org/inherited-annotations-in-Java/](https://www.geeksforgeeks.org/inherited-annotations-in-java/)

[Java 中的注释](https://www.geeksforgeeks.org/annotations-in-java/)有助于将元数据与程序元素相关联，例如类、实例变量、方法等。注释还可以用于将元数据附加到其他注释。这些类型的注释被称为元注释。默认情况下，Java 不允许继承自定义注释。@inherited 是一种元注释类型，用于注释自定义注释，以便子类可以继承这些自定义注释。下面提到了使用@继承注释的语法。

```
@Inherited
@interface CustomAnnotation {
    String value () default "GFG";
}
```

**场景:**

下面我们将讨论两种情况:

*   **Case 1:** Use @ to inherit comments.
*   **Case 2:** The @ inheritance comment is not used.

现在让我们讨论这两种场景，并将其实现为 java 程序，以便更好地理解它们。

**情况 1:** 使用@Inherited 注释

在下面显示的代码示例中，我们创建了一个名为 custom annotation 的自定义注释，并用@Inherited 注释对其进行了注释。我们使用自定义注释来注释被继承的超级类。InheritedAnnotationDemo 还继承了 CustomAnnotation，因为它是使用@Inherited 注释进行注释的。

**示例**

## Java

```
// Java Program to Illustrating Use of Custom Annotations
// With @inherited annotation

// Importing required classes from java.lang package
import java.lang.annotation.*;
import java.lang.reflect.AnnotatedElement;

// Creating our single valued custom annotation
// with @inherited annotation
@Inherited
@Target({ ElementType.TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)

// Custom annotation
@interface CustomAnnotation
{
    String value() default "GFG";
}

// Annotating the super class using
// the custom annotation
@CustomAnnotation(value = "Sky is limitless")

// Class 1
// Parent
class Super {
}

// Class 2
// Child class
// This is our derived class which inherits the
// the Super class and the custom annotation
public class InheritedAnnotationDemo extends Super {

    // Method 1
    // Main driver method
    public static void main(String[] arg) throws Exception
    {

        // Printing the annotation used to annotated the
        // Super and InheritedAnnotationDemo classes
        System.out.println(
            new InheritedAnnotationDemo()
                .getClass()
                .getAnnotation(CustomAnnotation.class));

        System.out.println(
            new Super().getClass().getAnnotation(
                CustomAnnotation.class));

        // Obtaining the class class name and
        // printing the annotation info about the
        //  annotation info attached to the Super class
        Class obj = Super.class;

        // Calling the method 2 to
        // print the annotation states
        printAnnotationState(obj);
    }

    // Method 2
    // To print the annotation state
    static void printAnnotationState(AnnotatedElement ann)
    {

        // Obtaining all the annotations attached to the
        // passed element and storing it in an array
        Annotation[] annotationsArray
            = ann.getAnnotations();

        // Iterating on all the annotations stored inside of
        // the array above and printing their information
        for (Annotation annotation : annotationsArray) {

            // Print and display nameand value of annotation
            System.out.println(
                "Name of the annotation : "
                + annotation.annotationType());
            System.out.println(
                "Value : "
                + ((CustomAnnotation)annotation).value());
        }
    }
}
```

**输出**

```
@CustomAnnotation(value="Sky is limitless")
@CustomAnnotation(value="Sky is limitless")
Name of the annotation : interface CustomAnnotation
Value : Sky is limitless
```

**情况 2:** 不使用@继承注释

在下面提到的代码示例中，除了我们没有使用@Inherited 注释来注释我们的 CustomAnnotation 之外，一切都是一样的。因此，自定义注释不会被 InheritedAnnotationDemo 类继承。因此，当我们对 InheritedAnnotationDemo 类使用 getAnnotation()方法时，它不会返回 CustomAnnotation。在这种情况下，如果我们没有使用任何注释来注释 InheritedAnnotationDemo 类，它只会返回 null。

**示例:**

## Java

```
// Java Program to Illustrating Use of Custom Annotations
// Without @inherited annotation

// Importing required classes from java.lang package
import java.lang.annotation.*;
import java.lang.reflect.AnnotatedElement;

// Creating our single valued custom
// annotation without @inherited annotation
@Target({ ElementType.TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
// Custom annotation
@interface CustomAnnotation
{
    String value() default "GFG";
}

// Annotating the super class using our
// custom annotation
@CustomAnnotation(value = "Sky is limitless")

// Class 1
class Super {
}

// Class 2
// Main class
// This is our derived class which inherits the
// the Super class but does not inherit the
// CustomAnnotation
public class InheritedAnnotationDemo extends Super {
    public static void main(String[] arg) throws Exception
    {

        // Printing the annotation used to annotated the
        // Super and InheritedAnnotationDemo classes
        System.out.println(
            new InheritedAnnotationDemo()
                .getClass()
                .getAnnotation(CustomAnnotation.class));

        // As we haven't used the @Inherited Annotation to
        // create the custom annotation therefore not
        // inherited by InheritedAnnotationDemo class. When
        // we use getAnnotation() now, returns null.
        System.out.println(
            new Super().getClass().getAnnotation(
                CustomAnnotation.class));

        // Obtaining the class class name and
        // printing the annotation info about the annotation
        // info attached to the Super class
        Class obj = Super.class;

        // Calling the Method 2 to
        // print the annotation state
        printAnnotationState(obj);
    }

    // Method 2
    // To print the annotation state
    static void printAnnotationState(AnnotatedElement ann)
    {

        // Obtaining all the annotations attached to the
        // passed element and storing it in an array
        Annotation[] annotationsArray
            = ann.getAnnotations();

        // Iterating on all the annotations stored inside of
        // the array above and printing their information
        for (Annotation annotation : annotationsArray) {

            // Print and display name and value of the the
            // annotation
            System.out.println(
                "Name of the annotation : "
                + annotation.annotationType());
            System.out.println(
                "Value : "
                + ((CustomAnnotation)annotation).value());
        }
    }
}
```

**输出**

```
null
@CustomAnnotation(value="Sky is limitless")
Name of the annotation : interface CustomAnnotation
Value : Sky is limitless
```