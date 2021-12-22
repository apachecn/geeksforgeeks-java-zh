# Java 程序演示一个没有参数和返回类型的方法

> 原文:[https://www . geesforgeks . org/Java-program-to-installation-a-method-不带参数和返回类型/](https://www.geeksforgeeks.org/java-program-to-illustrate-a-method-without-parameters-and-return-type/)

函数是将程序分解成不同模块的一种方式，这些模块一个接一个地执行。要在 Java 中使用函数，我们需要:

*   Declare a function, that is, the prototype of a declaration function.
*   Define functions
*   Call function

重要的是，我们在调用函数之前声明它，并且定义可以保存在程序的任何部分。

**声明、定义和调用函数**

现在我们将创建一个没有返回类型和参数的函数。在声明一个函数时，我们需要指定函数的返回类型以及它将要接受的参数的数量和类型。对于返回类型，我们有 int、float、char 等选项。但是有时我们不需要返回任何东西，在这种情况下，我们必须使用 **void** 返回类型。因为我们也不会传递任何参数，所以我们必须在声明时通过保持括号为空来指定它。

**示例:**

## Java

```java
// Java Program to Illustrate a Method with No Parameters
// and Return Type

public class Main {

    // Declaration and Definition of the function 
    public static void greet()
    {
        System.out.println(
            "Hey Geeks! Welcome to NoWhere.");

        /* Optional program will work same
           without this return statement */
        return;
    }
    public static void main(String args[])
    {
        // Calling of the function without any parameters
        greet();
    }
}
```

**输出**

```java
Hey Geeks! Welcome to NoWhere.

```

在上面的程序中，我们在相同的地方声明和定义函数，这是可以做到的，如果我们想在声明函数的同一个程序中使用它，这也被认为是好的。另外，您可以注意到声明和调用期间的参数是空的，因为我们没有传递任何参数。甚至我们没有存储来自函数的任何数据，因为函数没有返回任何东西。

**注意:**可以在函数的末尾使用 return 语句，但是它是完全可选的。如果删除 return 语句，程序将以与 return 语句相同的方式运行。