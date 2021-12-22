# 如何使用 Optional 类避免 Java 中的 NullPointerException？

> 原文:[https://www . geeksforgeeks . org/如何避免-nullpointerexception-in-Java-use-optional-class/](https://www.geeksforgeeks.org/how-to-avoid-nullpointerexception-in-java-using-optional-class/)

为了学会如何避免错误，我们必须首先了解错误。

**[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)**

**NullPointerException** 是一个 RuntimeException。在 [Java](https://www.geeksforgeeks.org/java/) 中，可以为对象引用分配一个特殊的空值。当程序试图使用具有空值的对象引用时，会引发 NullPointerException。

这些可以是:

*   从空对象调用方法。
*   访问或修改空对象的字段。
*   取 null 的长度，就像它是一个数组一样。
*   访问或修改空对象的槽，就像它是一个数组一样。
*   抛出 null，就好像它是一个可抛出的值。
*   当您尝试在空对象上同步时。

**示例:**

```java
// Java program to show NullPointerException

public class Example {
    public static void main(String[] args)
    {

        // Create a String of size 10
        String[] a = new String[10];

        // The String is empty
        // So a[1] will have null at present
        String upcase = a[1].toUpperCase();

        System.out.print(upcase);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
    at Example.main(Example.java:4)

```

**如何用可选类避免 NullPointerException？:**
Java 8 在 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中引入了新的[类可选](https://www.geeksforgeeks.org/java-8-optional-class/)。它可以在不使用太多空检查的情况下帮助编写一个整洁的代码。通过使用可选，我们可以指定要返回的替代值或要运行的替代代码。这使得代码更易读，因为隐藏的事实现在对开发人员来说是可见的。

**可选类**
可选是一个可以包含非空值或空值的容器对象。它基本上检查内存地址是否有对象。如果存在值，is present()将返回 true，get()将返回该值。还提供了依赖于包含值的存在与否的其他方法，例如 orElse()和 ifPresent()，前者在值不存在时返回默认值，后者在值存在时执行一个代码块。这是一个基于值的类，即它们的实例是:

*   Final 和不可变的(尽管可能包含对可变对象的引用)。
*   仅基于 equals()而不是基于引用等式(==)被视为相等。
*   Do not have accessible constructors.

    **语法:**

    ```java
    Optional is a generic type of type T.

    Optional<T>

    ```

    **使用可选类**纠正上述空指针异常的代码

    ```java
    // Java program to avoid NullPointerException
    // using Optional Class

    import java.util.Optional;

    public class Example {
        public static void main(String[] args)
        {

            // Create a String of size 10
            String[] a = new String[10];

            // Create an Optional Class instance
            // and get the state for a[1] element
            // for Null value
            Optional<String> check = Optional.ofNullable(a[1]);

            // If the value in the current instance is null,
            // it will return false, else true
            if (check.isPresent()) {

                // The String is empty
                // So a[1] will have null at present
                String upcase = a[1].toUpperCase();
                System.out.print(upcase);
            }
            else

                // As the current value is null
                System.out.println("String value is not present");
        }
    }
    ```

    **Output:**

    ```java
    String value is not present

    ```

    **注意:**因此这可以理解为一种针对 NullPointerException 的异常处理方法

    **使用可选类处理空指针异常:**

    ```java
    // Java program to handle NullPointerException
    // using Optional Class

    import java.util.Optional;

    public class Example {
        public static void main(String[] args)
        {

            // Create a String of size 10
            String[] a = new String[10];

            // Define the a[1] element
            a[1] = "geeksforgeeks";

            // Create an Optional Class instance
            // and get the state for a[1] element
            // for Null value
            Optional<String> check = Optional.ofNullable(a[1]);

            // If the value in the current instance is null,
            // it will return false, else true
            if (check.isPresent()) {

                // The String is not empty
                // So a[1] will have a value at present
                String upcase = a[1].toUpperCase();
                System.out.print(upcase);
            }
            else

                // If the current value is null
                System.out.println("String value is not present");
        }
    }
    ```

    **Output:**

    ```java
    GEEKSFORGEEKS

    ```