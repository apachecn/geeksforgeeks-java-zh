# Java 中的断言

> 原文:[https://www.geeksforgeeks.org/assertions-in-java/](https://www.geeksforgeeks.org/assertions-in-java/)

断言允许测试程序中任何假设的正确性。

断言是使用 Java 中的**断言**语句实现的。在执行断言时，它被认为是正确的。如果失败，JVM 会抛出一个名为**的错误。**主要用于开发过程中的测试目的。

**assert** 语句与布尔表达式一起使用，可以用两种不同的方式编写。

**第一种方式:**

```
*assert* *expression;*
```

**第二路:**

```
*assert* *expression1 : expression2;*
```

***断言示例:-***

```
*// Java program to demonstrate syntax of assertion
import java.util.Scanner;

class Test
{
    public static void main( String args[] )
    {
        int value = 15;
        assert value >= 20 : " Underweight";
        System.out.println("value is "+value);
    }
}*
```

***输出:***

```
*value is 15*
```

*启用断言
后**输出:***

```
*Exception in thread "main" java.lang.AssertionError: Underweight*
```

***使能断言***

*默认情况下，断言是禁用的。我们需要运行给定的代码。在 Java 源代码中启用断言语句的语法是:*

```
***java –ea** Test*
```

*或者*

```
***java –enableassertions** Test*
```

*这里，Test 是文件名。*

***禁用断言***

*在 java 中禁用断言的语法是:*

```
***java –da** Test*
```

*或者*

```
***java –disableassertions** Test*
```

*这里，Test 是文件名。*

***为什么要使用断言**
无论程序员想看他/她的假设是否错误。*

*   *以确保看起来不可达的代码实际上是不可达的。*
*   *确保写在评论里的假设是正确的。

    ```
             if ((x & 1) == 1)  
             {  }
             else // x must be even 
             { assert (x % 2 == 0); }
    ```* 
*   *确保没有达到默认开关情况。*
*   *检查对象的状态。*
*   *在方法的开始*
*   *方法调用后。*

***断言 Vs 正常异常处理**
断言主要用于检查逻辑上不可能的情况。例如，它们可以用来检查代码在开始运行前的预期状态或在结束运行后的状态。与正常的异常/错误处理不同，断言通常在运行时被禁用。*

*****在哪里使用断言*****

*   ***私有方法的参数。私有参数仅由开发人员的代码提供，开发人员可能希望检查他/她对参数的假设。***
*   ***有条件的情况。***
*   ***任何方法开头的条件。***

*****不使用断言的地方*****

*   ***断言不应用于替换错误消息***
*   ***断言不应用于检查公共方法中的参数，因为它们可能由用户提供。错误处理应该用于处理用户提供的错误。***
*   ***断言不应用于命令行参数。***

*****相关文章:**
[C/c++](http://geeksquiz.com/assertions-cc/)中的断言***

*****本文由**拉胡尔·阿加尔瓦尔**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。*****