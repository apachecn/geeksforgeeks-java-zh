# 在 Java 中阻塞 Lambda 表达式

> 原文:[https://www . geesforgeks . org/block-lambda-expressions-in-Java/](https://www.geeksforgeeks.org/block-lambda-expressions-in-java/)

**Lambda 表达式**是一个不单独执行的未命名方法。这些表达式导致匿名类。这些 lambda 表达式称为闭包。Lambda 的主体由一段代码组成。如果只有一个单独的表达式，它们被称为“[表达式主体](https://www.geeksforgeeks.org/lambda-expressions-java-8/)”。包含表达体的 Lambdas 被称为“[表达 Lambdas](https://www.geeksforgeeks.org/lambda-expressions-java-8/) ”。下面是单行的 Lambda 表达式示例。

块 lambda 包含许多对 lambda 表达式起作用的操作，因为它允许 Lambda 主体有许多语句。这包括变量、循环、条件语句，如 if、else 和 switch 语句、嵌套块等。这是通过将 lambda 主体中的语句块包含在大括号{}中来创建的。这甚至可以有一个返回语句，即返回值。

**语法:**λ表达式

```java
(parameters) -> { lambda body }
```

现在，首先让我们了解一下 Lambda 表达式，以了解 block lambda 表达式。

插图:

在这种情况下，lambda 在其 lambda 主体中可能需要不止一个表达式。Java 支持表达式 Lambdas，它包含具有多个语句的代码块。我们称这种类型的λ体为“ ***”块状体*** ”。包含块体的 Lambda 可称为“***Block Lambda*****s**”。

**代表λ表达式的示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Lambda expression

// Importing input output classes
import java.io.*;

// Interface
// If1 is name of this interface
interface If1 {

    // Member function of this interface
    // Abstract function
    boolean fun(int n);
}

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Lambda expression body
        If1 isEven = (n) -> (n % 2) == 0;

        // Above is lambda expression which tests
        // passed number is even or odd

        // Condition check over some number N
        // by calling the above function
        // using isEven() over fun() defined above

        // Input is passed as a parameter N
        // Say custom input N = 21
        if (isEven.fun(21))

            // Display message to be printed
            System.out.println("21 is even");
        else

            // Display message to be printed
            System.out.println("21 is odd");
    }
}
```

**Output**

```java
21 is odd
```

现在切换到块λ表达式的实现，后面有两个例子，如下所示:

**实施:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Block Lambda expression

// Importing all classes from
// java.util package
import java.io.*;

// Block lambda to find out factorial
// of a number

// Interface
interface Func {
    // n is some natural number whose
    // factorial is to be computed
    int fact(int n);
}

// Class
// Main class
class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Block lambda expression
        Func f = (n) ->
        {
            // Block body

            // Initially initializing with 1
            int res = 1;

            // iterating from 1 to the current number
            // to find factorial by multiplication
            for (int i = 1; i <= n; i++)
                res = i * res;
            return res;
        };

        // Calling lambda function

        // Print and display n the console
        System.out.println("Factorial of 5 : " + f.fact(5));
    }
}
```

**Output**

```java
Factorial of 5: 120
```

> 在这个块中，lambda 声明了一个变量“res”，用于循环，并具有在 lambda 主体中合法的返回语句。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Block Lambda expression

// Importing all input output classes
import java.io.*;

// Interface
// Functional interface named 'New'
interface New {

    // Boolean function to check over
    // natural number depicting calender year

    // 'n' deepicting year is
    // passed as an parameter
    boolean test(int n);
}

// Class
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // block lambda
        // This block lambda checks if the
        // given year is leap year or not
        New leapyr = (year) ->
        {
            // Condition check
            // If year is divisible by 400 or the
            // year is divisible by 4 and 100 both
            if (((year % 400 == 0)
                 || (year % 4 == 0) && (year % 100 != 0)))

                // Returning true as year is leap year
                return true;
            else

                // Returning false for non-leap years
                return false;
        };

        // Calling lambda function over
        // custom input year- 2020

        // Condition check using the test()
        // defined in the above interface
        if (leapyr.test(2020))

            // Display message on the console
            System.out.println("leap year");
        else

            // Display message on the console
            System.out.println("Non leap year");
    }
}
```

**Output**

```java
leap year
```

> 在这个块中，lambda 有 if-else 条件和返回语句，它们在 lambda 主体中是合法的。