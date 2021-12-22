# 如何用 Java 创建自己的注释？

> 原文:[https://www . geesforgeks . org/如何用 java 创建自己的注释/](https://www.geeksforgeeks.org/how-to-create-your-own-annotations-in-java/)

注释是元数据的一种形式，它提供关于程序的信息，但不是程序本身的一部分。注释不会影响它们注释的代码的操作。

现在让我们来看看不同类型的 java 注释，如下所示:

1.  **预定义注释**.:@已弃用、@覆盖、@抑制警告、@安全参数、@功能接口.
2.  **Meta comments** : @ reserved, @ recorded, @ target, @ inherited, @ repeatable.
3.  **User-defined label** : these are defined by the user. (We will learn to create custom annotations in this module).

极客，现在你一定想知道我们如何创建自己的 java 注释，为此，请依次参考以下简单步骤:

1.  To create your own Java annotation, you must use **@ Interface annotation _ name,** which will create a new Java annotation for you.
2.  **@ Interface** will describe the new annotation type declaration.
3.  After naming your comments, you need to create a statement block in which you can declare some variables.

现在继续，有三种形式的注释可以用 java 定义如下:

1.  **标记注释:**这些是内部没有声明或定义变量的注释。
2.  **单值注释:**这些注释中只声明或定义了一个变量。
3.  **多值注释:**这些是可以声明和定义多种类型的多个变量的注释。

**实施:**

让我们以一个名为 **books_data** 的自定义注释为例，来了解不同形式的注释是如何声明的。

```java
@interface books_data //using the syntax : @interface Annotation_name, we declared a new annotation here.
{ //beginning of annotation declaration and defination

/*
defining variables inside an annotation is optional.
The number of variables declared inside an annotation will describe its form.
*/

} //end of annotation declaration and defination
```

**例 1:**

## Java

```java
// Java Programwhere Illustrating Declaration of
// Custom Marker Annotation

// Importing I/O classes
import java.io.*;

// Sample for marker Annotation:
// Custom annotation declaration
@interface books_data
{
    // No variable declared here
}

// Main class
class books {

    // Main driver method
    public static void main(String[] args)
    {
        // Print statement
        System.out.println(
            "example of Marker Annotations.");
    }
}
```

**Output**

```java
example of Marker Annotations.
```

> 由于在这个标注里面没有声明变量，这将被称为**标记标注。**

**例 2:**

## 爪哇

```java
// Java Program Illustrating Declaration of
// Custom Single Value Annotation

// Importing input output classes
import java.io.*;

// Sample for single value Annotation:
// Custom annotation declaration
@interface books_data
{
    // Single variable declaration
    String book_name();
}

// Main class
class books {

    // Main driver method
    public static void main(String[] args)
    {
        // Print statement
        System.out.println(
            "example of single value Annotation.");
    }
}
```