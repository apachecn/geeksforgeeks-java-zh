# 系统参考 Java 的软件系统的向后兼容性

> 原文:[https://www . geesforgeks . org/向后兼容软件系统对 java 的系统引用/](https://www.geeksforgeeks.org/backwards-compatibility-in-a-software-system-with-systematic-reference-to-java/)

在这里，我们将讨论在任何软件系统中开发新功能时实现“向后兼容性”的方法。因此，让我们简要地介绍一下向后兼容性。**向后兼容性**是系统、产品或技术的一种属性，允许与旧的遗留系统或为这种系统设计的输入集成。以不允许向后兼容的方式修改系统被称为“中断更改”尽管当前的敏捷软件开发时代要求快速实现功能以满足快速变化的需求，但是在开发的软件中具有向后兼容性是极其必要的。

在这里，我们将讨论 java 如何在开发新特性时实现向后兼容，这将作为更新现有代码时的潜在参考。

现在让我们来了解一下‘T0’加宽‘T1’的非常重要的概念，以及在开发像 Java 5 中的[自动装箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)这样的新特性时如何保留它。在具有重载方法的类中，编译器的工作之一是每当发现重载方法的调用时，就确定使用哪个方法。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Without Involving Concepts
// of Java 5 Features

// Importing required classes
import java.io.*;

// Main class
// To test method overloading
class GFG {

    // Method 1
    static void print(int i)
    {
        // Print statement when method 1 is called
        System.out.println("int = " + i);
    }

    // Method 2
    static void print(long l)
    {
        // Print statement when method 2 is called
        System.out.println("long = " + l);
    }

    // Method 3
    static void print(double d)
    {
        // Print statement when method 3 is called
        System.out.println("double = " + d);
    }

    // Method 4
    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing variables
        byte b = 5;
        short s = 5;
        long l = 5;
        float f = 5.0f;

        // Calling the methods
        print(b);
        print(s);
        print(l);
        print(f);
    }
}
```

**Output**

```
int = 5
int = 5
long = 5
double = 5.0
```

当使用*字节*和*短*参数调用一个方法时，Java 编译器隐式地将其扩展，以匹配接受 int 参数的 *print()* 方法的适当版本。此外，可以看出，当使用 *long* 调用打印方法时，它使用打印方法 *print(long l)* 的各个版本，并且使用 *float* 的方法调用与使用 *double 的方法相匹配，因此，*依次解释*和*加宽[的行为。](https://www.geeksforgeeks.org/method-overloading-autoboxing-widening-java/)

> [**Note:** *当没有找到精确匹配时，JVM 使用具有最小可能参数的方法，该参数比传递的参数更宽。*](https://www.geeksforgeeks.org/method-overloading-autoboxing-widening-java/)

**例 2:** 这里我们将只有一个方法接受*双*作为参数。当用*字节、短、长*、和*浮点*调用时，它将匹配 *print()* 方法

## Java

```
// Main class
// To test Method Overloading
class TestMethodOverloading {

    static void print(double d)
    {
        System.out.println("double = " + d);
    }
    public static void main(String[] args)
    {
        byte b = 5;
        short s = 5;
        long l = 5;
        float f = 5.0f;
        print(b);
        print(s);
        print(l);
        print(f);
    }
}
```

**输出**

```
double = 5.0
double = 5.0
double = 5.0
double = 5.0
```

T23】的所有四个调用

现在让我们讨论一下我们在 Java5 中的特性，即自动装箱。[自动装箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)是 Java 5 中引入的关键特性之一。自动装箱是 Java 编译器在原语类型和它们对应的对象包装类之间进行的自动转换。例如，将整数转换为整数，将双精度转换为双精度，等等。所以发挥 Java 5 向后兼容的概念。关于自动装箱，考虑下面的例子，它将帮助我们理解 Java 如何在引入新特性的同时保持向后兼容性。

**示例**

## Java

```
// Java Program Illustrating Maintenance of Backward
// Compatibility

// Importing required classes
import java.io.*;

// Main class
// To test backwards compatibility
class GFG {

    // Method 1
    static void print(Integer i)
    {
        // Print statement whenever method 1 is called
        System.out.println("Integer = " + i);
    }

    // Method 2
    static void print(long l)
    {
        // Print statement whenever method 1 is called
        System.out.println("long = " + l);
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {
        int i = 5;

        // Calling method over above custom input
        print(i);
    }
}
```

**输出**

```
long = 5
```

从上面的输出中得到的经验如下:

*   If only one version of *print ()* method accepts a *integer* , then referring to the automatic packing function of Java 5, calling *print ()* will be successful. Similarly, if only a long version exists, the compiler will call the same version.
*   If both methods exist, which one will be used? Therefore, in order to establish backward compatibility, the compiler thinks that widening primitive parameters is preferable to performing automatic boxing operation, so the compiler will choose widening instead of boxing, and the output is

**结论:**在本文中，我们已经看到了在用示例开发新特性时，如何维护以及需要考虑的事情，以实现“向后兼容”。随着 Java 5 中新的“自动装箱”功能的引入，Java 设计人员更倾向于现有功能“加宽”。一个重要的规则是，预先存在的代码应该像以前一样运行，所以编译器总是在选择新的样式之前选择旧的样式(加宽而不是自动装箱)。