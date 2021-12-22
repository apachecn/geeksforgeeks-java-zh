# 使用最终块捕获异常的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序到使用-最终-阻止捕获-异常/](https://www.geeksforgeeks.org/java-program-to-use-finally-block-for-catching-exceptions/)

java 中的[**final block**](https://www.geeksforgeeks.org/g-fact-24-finalfinally-and-finalize-in-java/)用于放置重要代码，如清理代码，例如关闭文件或关闭连接。不管异常是否出现，也不管异常是否被处理，最终块都会执行。不管异常是否发生，最终都会包含所有关键语句。

**有 3 种可能的情况可以使用 finally block:**

**情况 1:** 当异常没有出现时

在这种情况下，程序运行良好，没有抛出任何异常，最后在 try 块之后阻塞执行。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// finally block in java When
// exception does not rise 

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            System.out.println("inside try block");

            // Not throw any exception
            System.out.println(34 / 2);
        }

        // Not execute in this case
        catch (ArithmeticException e) {

            System.out.println("Arithmetic Exception");

        }
        // Always execute
        finally {

            System.out.println(
                "finally : i execute always.");

        }
    }
}
```

**Output**

```java
inside try block
17
finally : i execute always.
```

**情况 2:** 当异常上升并由 catch 块处理时

在这种情况下，程序抛出异常，但由 catch 块处理，最后块在 catch 块之后执行。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate finally block in java
// When exception rise and handled by catch

import java.io.*;

class GFG {

    public static void main(String[] args)
    {
        try {
            System.out.println("inside try block");

            // Throw an Arithmetic exception
            System.out.println(34 / 0);
        }

        // catch an Arithmetic exception
        catch (ArithmeticException e) {

            System.out.println(
                "catch : exception handled.");
        }

        // Always execute
        finally {  

          System.out.println("finally : i execute always.");
        }
    }
}
```

**Output**

```java
inside try block
catch : exception handled.
finally : i execute always.
```

**情况 3:** 异常上升且未被捕捉块处理时

在这种情况下，程序抛出了一个异常，但没有被 catch 处理，因此 finally block 在 try block 之后执行，并且在 finally block 执行之后程序异常终止，但是 finally block 执行正常。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate finally block 
// When exception rise and not handled by catch

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            System.out.println("Inside try block");

            // Throw an Arithmetic exception
            System.out.println(34 / 0);
        }

        // Can not accept Arithmetic type exception
        // Only accept Null Pointer type Exception
        catch (NullPointerException e) {

            System.out.println(
                "catch : exception not handled.");
        }

        // Always execute
        finally {

            System.out.println(
                "finally : i will execute always.");
        }
        // This will not execute
        System.out.println("i want to run");
    }
}
```

**输出**

```java
Inside try block
finally : i will execute always.
Exception in thread "main" java.lang.ArithmeticException: / by zero
    at GFG.main(File.java:10)
```