# Java 中的歧义

> 原文:[https://www.geeksforgeeks.org/ambiguities-in-java/](https://www.geeksforgeeks.org/ambiguities-in-java/)

歧义是那些在 Java 语言规范中没有明确定义的问题。不同编译器在几个示例程序上产生的不同结果支持了我们的观察。这里我们将按以下顺序讨论。

*   Ambiguity method in method overload
    *   Method with Varargs parameter only
    *   Methods with Varargs and other parameters
*   Ambiguity in multiple inheritance
    *   Diamond problem

**类型 1:** 方法重载中的歧义方法

当您重载方法时，您有可能造成一种不明确的情况，即编译器无法确定使用哪种方法。例如，考虑以下重载的 *computeBalance()* 方法声明:

```
public static void computeBalance(double deposit)
```

```
public static void computeBalance(double withdrawal)
```

如果声明一个名为 myDeposit 的双变量，并进行方法调用，如 computeBalance(my deposit)；，你就会制造出一个模棱两可的局面。这两种方法都与您的调用完全匹配。您可能会争辩说，使用名为“myDeposit”的变量的调用似乎应该转到参数名为 Deposit 的方法版本，但是 Java 并没有基于变量名做出假设。computeBalance()的每个版本都可以接受一个双精度值，Java 不会假设您打算使用哪个。

**模糊错误**

泛型的引入导致了一种新的错误，你必须防止歧义。当擦除导致两个看似不同的泛型声明解析为相同的擦除类型，从而导致冲突时，就会出现模糊错误。下面是一个涉及方法重载的示例。

现在我们可以用上面显示的类型 1 来描述。varargs 中的方法重载

重载允许不同的方法具有相同的名称，但签名不同，其中签名可能因输入参数的数量或输入参数的类型或两者而异。我们可以通过以下方式重载接受可变长度参数的方法:

**情况 1:** 仅使用 Varargs 参数的方法

在这种情况下，Java 使用类型差异来确定调用哪个重载方法。如果一个方法签名严格来说比另一个更具体，那么 Java 会毫无错误地选择它。

**示例**

## Java

```
// Java program to illustrate method overloading in varargs

// Main class demonstrating varargsDemo
public class GFG {

    // Method 1
    // varargs method with float datatype
    static void fun(float... x)
    {

        // Print statement
        // whenever this method is called
        System.out.println("float varargs");
    }

    // Method 2
    // varargs method with int datatype
    static void fun(int... x)
    {

        // Print statement
        // whenever this method is called
        System.out.println("int varargs");
    }

    // Method 3
    // varargs method with double datatype
    static void fun(double... x)
    {

        // Print statement
        // whenever this method is called
        System.out.println("double varargs");
    }

    // Method 4
    // Main driver method
    public static void main(String[] args)
    {

        // Calling the above methods
        fun();
    }
}
```

**输出**

```
int varargs
```