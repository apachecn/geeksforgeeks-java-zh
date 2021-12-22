# 试捕中的流量控制最后在 Java 中

> 原文:[https://www . geesforgeks . org/flow-control-in-try-catch-finally-in-Java/](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/)

在本文中，我们将探索 try-catch-finally 的所有可能组合，无论何时引发异常，以及在每个给定的情况下控制流是如何发生的。

1.  **尝试-捕获子句或尝试-捕获-最终子句中的控制流**
    *   **情况 1:** 异常发生在 try 块中，在 catch 块中处理
    *   **情况 2:** 异常发生在尝试块中，不在 catch 块中处理
    *   **情况 3:** 尝试块中没有出现异常
2.  **尝试-最终条款**
    *   **情况 1:** 尝试块出现异常
    *   **情况 2:** 尝试块中没有出现异常

**试捕或试捕中的控制流程-最终**

**1。异常发生在 try 块中，并在 catch 块中处理:**如果 try 块中的语句引发了异常，则 try 块的其余部分不会执行，控制将传递给对应的**catch 块。在执行 catch 块之后，控制将被转移到 finally 块(如果存在的话)，然后剩余的程序将被执行。**

*   ****试捕中的控制流程:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// control flow of try-catch clause
// when exception occur in try block
// and handled in catch block
class GFG
{
    public static void main (String[] args)
    {

        // array of size 4.
        int[] arr = new int[4];
        try
        {
            int i = arr[4];

            // this statement will never execute
            // as exception is raised by above statement
            System.out.println("Inside try block");
        }
        catch(ArrayIndexOutOfBoundsException ex)
        {
            System.out.println("Exception caught in Catch block");
        }

        // rest program will be executed
        System.out.println("Outside try-catch clause");
    }
}
```

**输出:**

```java
Exception caught in Catch block
Outside try-catch clause
```

*   ****try-catch-finally 子句中的控制流:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// control flow of try-catch-finally clause
// when exception occur in try block
// and handled in catch block
class GFG
{
    public static void main (String[] args)
    {

        // array of size 4.
        int[] arr = new int[4];

        try
        {
            int i = arr[4];

            // this statement will never execute
            // as exception is raised by above statement
            System.out.println("Inside try block");
        }

        catch(ArrayIndexOutOfBoundsException ex)
        {
            System.out.println("Exception caught in catch block");
        }

        finally
        {
            System.out.println("finally block executed");
        }

        // rest program will be executed
        System.out.println("Outside try-catch-finally clause");
    }
}
```

**输出:**

```java
Exception caught in catch block
finally block executed
Outside try-catch-finally clause
```

****2。try-block 中发生的异常没有在 catch block 中处理:**在这种情况下，将遵循默认的处理机制。如果 finally 块存在，它将按照默认处理机制执行。**

*   ****试捕条款:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// control flow of try-catch clause
// when exception occurs in try block
// but not handled in catch block
class GFG
{
    public static void main (String[] args)
    {

        // array of size 4.
        int[] arr = new int[4];
        try
        {
            int i = arr[4];

            // this statement will never execute
            // as exception is raised by above statement
            System.out.println("Inside try block");
        }

        // not a appropriate handler
        catch(NullPointerException ex)
        {
            System.out.println("Exception has been caught");
        }

        // rest program will not execute
        System.out.println("Outside try-catch clause");
    }
}
```

**运行时错误:**

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 4
    at GFG.main(GFG.java:12)
```

*   ****try-catch-finally 子句:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// control flow of try-catch-finally clause
// when exception occur in try block
// but not handled in catch block
class GFG
{
    public static void main (String[] args)
    {

        // array of size 4.
        int[] arr = new int[4];

        try
        {
            int i = arr[4];

            // this statement will never execute
            // as exception is raised by above statement
            System.out.println("Inside try block");
        }

        // not a appropriate handler
        catch(NullPointerException ex)
        {
            System.out.println("Exception has been caught");
        }

        finally
        {
            System.out.println("finally block executed");
        }

        // rest program will not execute
        System.out.println("Outside try-catch-finally clause");
    }
}
```

**输出:**

```java
finally block executed
```

**运行时错误:**

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 4
    at GFG.main(GFG.java:12)
```

****3。异常不会在 try-block 中发生:**在这种情况下，catch block 永远不会运行，因为它们只在异常发生时运行。最后块(如果存在)将被执行，然后是程序的其余部分。**

*   ****试捕条款:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate try-catch
// when an exception doesn't occurred in try block
class GFG
{
    public static void main (String[] args)
    {

        try
        {

            String str = "123";

            int num = Integer.parseInt(str);

            // this statement will execute
            // as no any exception is raised by above statement
            System.out.println("Inside try block");

        }

        catch(NumberFormatException ex)
        {

            System.out.println("catch block executed...");

        }

        System.out.println("Outside try-catch clause");
    }
}
```

**输出:**

```java
Inside try block
Outside try-catch clause
```

*   ****尝试-捕捉-最终条款****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate try-catch-finally
// when exception doesn't occurred in try block
class GFG
{
    public static void main (String[] args)
    {

    try
    {

        String str = "123";

        int num = Integer.parseInt(str);

        // this statement will execute
        // as no any exception is raised by above statement
        System.out.println("try block fully executed");

    }

    catch(NumberFormatException ex)
    {

        System.out.println("catch block executed...");

    }

    finally
    {
        System.out.println("finally block executed");
    }

    System.out.println("Outside try-catch-finally clause");
    }
}
```

**输出:**

```java
try block fully executed
finally block executed
Outside try-catch clause
```

****尝试中的控制流程-最终****

**在这种情况下，无论 try-block 中是否出现异常，**最终总是会被执行。**但是控制流程将取决于尝试块中是否出现异常。**

****1。引发异常:**如果在 try 块中出现异常，则控制流将最终被阻止，随后是默认的异常处理机制。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// control flow of try-finally clause
// when exception occur in try block
class GFG
{
    public static void main (String[] args)
    {

        // array of size 4.
        int[] arr = new int[4];
        try
        {
            int i = arr[4];

            // this statement will never execute
            // as exception is raised by above statement
            System.out.println("Inside try block");
        }

        finally
        {
            System.out.println("finally block executed");
        }

        // rest program will not execute
        System.out.println("Outside try-finally clause");
    }
}
```

**输出:**

```java
finally block executed
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 4
    at GFG.main(GFG.java:11)
```

****2。未引发异常:**如果在 try 块中未发生异常，则控制流将最终被阻止，然后是程序的其余部分**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// control flow of try-finally clause
// when exception doesn't occur in try block
class GFG
{
    public static void main (String[] args)
    {

        try
        {
            String str = "123";

            int num = Integer.parseInt(str);

            // this statement will execute
            // as no any exception is raised by above statement
            System.out.println("Inside try block");
        }

        finally
        {
            System.out.println("finally block executed");
        }

        // rest program will be executed
        System.out.println("Outside try-finally clause");
    }
}
```

**输出:**

```java
Inside try block
finally block executed
Outside try-finally clause
```

****相关文章:****

*   **[Java 中的投掷和投掷](https://www.geeksforgeeks.org/throw-throws-java/)**
*   **[Java 中异常的类型](https://www.geeksforgeeks.org/types-of-exception-in-java/)**
*   **[Java 中已检查与未检查的异常](https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/)**

**本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**