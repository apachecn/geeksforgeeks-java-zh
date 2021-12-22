# 用 Java 打印异常消息的不同方式

> 原文:[https://www . geeksforgeeks . org/不同的打印方式-异常消息-in-java/](https://www.geeksforgeeks.org/different-ways-to-print-exception-messages-in-java/)

在 Java 中，有三种方法可以打印异常信息。他们都在可投掷类中。因为 Throwable 是所有异常和错误的基类，所以我们可以在任何异常对象上使用这三种方法。

### Java 中打印异常的方法

Java 中有三种方法可以打印异常消息。这些是:

**1。Java . lang . throwable . printstacktrace()方法:**

通过使用这个方法，我们将在下一行中获得由冒号分隔的异常的名称(例如 java.lang.ArithmeticException)和描述(例如/ by zero)，以及堆栈跟踪(其中代码表示该异常已经发生)。

**语法:**

```java
public void printStackTrace()
```

## Java

```java
// Java program to demonstrate
// printStackTrace method

public class Test {
    public static void main(String[] args)
    {
        try {
            int a = 20 / 0;
        }
        catch (Exception e) {
            // printStackTrace method
            // prints line numbers + call stack
            e.printStackTrace();

            // Prints what exception has been thrown
            System.out.println(e);
        }
    }
}
```

**运行时异常:**

```java
java.lang.ArithmeticException: / by zero
    at Test.main(Test.java:9)
```

**输出:**

```java
java.lang.ArithmeticException: / by zero
```

**2。** [**托斯特林()法**](https://www.geeksforgeeks.org/overriding-tostring-method-in-java/) **:**

使用此方法只会获取异常的名称和描述。请注意，这个方法在 Throwable 类中被重写。

## 爪哇

```java
// Java program to demonstrate
// toString  method

public class Test {
    public static void main(String[] args)
    {
        try {
            int a = 20 / 0;
        }
        catch (Exception e) {
            // toString method
            System.out.println(e.toString());

            // OR
            // System.out.println(e);
        }
    }
}
```

**输出**

```java
java.lang.ArithmeticException: / by zero
```

**3。java.lang.Throwable.getMessage()方法:**

使用这种方法，我们只会得到一个异常的描述。

**语法:**

```java
public String getMessage()
```

## Java

```java
// Java program to demonstrate
// getMessage method

public class Test {
    public static void main(String[] args)
    {
        try {
            int a = 20 / 0;
        }
        catch (Exception e) {
            // getMessage method
            // Prints only the message of exception
            // and not the name of exception
            System.out.println(e.getMessage());

            // Prints what exception has been thrown
            // System.out.println(e);
        }
    }
}
```

**输出**

```java
/ by zero
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。