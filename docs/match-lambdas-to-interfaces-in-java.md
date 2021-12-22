# 将 Lambdas 与 Java 中的接口进行匹配

> 原文:[https://www . geesforgeks . org/match-lambdas-to-interfaces-in-Java/](https://www.geeksforgeeks.org/match-lambdas-to-interfaces-in-java/)

最受欢迎和最重要的话题之一是 java 中的 [lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)但是在直接进入我们的讨论之前，让我们对一些重要的事情有所了解。从 java 中的接口作为接口开始，引用类型类似于类，但只包含抽象方法。这是我们在 java 1.8 之前对接口的定义。在 java 版本之前，我们使用的是任何版本，接口有三种类型，即如下所示:

*   Ordinary interface
*   Multi-method interface.
*   Tag (the interface does not contain any methods).

> 从 1.8 开始所有 SAM(单一抽象方法)接口被称为*功能接口。*

**Functional Interface:**Functional Interface 是一个只包含一个抽象方法的接口，但重要的一点是要记住，它可以有任意数量的默认或静态方法以及对象类方法，因为这最让程序员困惑。

**例:**

## 爪哇

```
// Java Program to Illustrate Functional Interface

// Importing required classes
import java.io.*;

// Interface
@FunctionalInterface
interface display {

    // Attribute
    void show(String msg);

    // Method
    // To compute the sum
    default int doSum(int a, int b) { return a + b; }
}

// Main class implementing the above interface
class GFG implements display {

    // Overriding the existing show() method
    @Override

    public void show(String msg)
    {

        // Print message
        System.out.println(msg);
    }

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of class inside main()
        GFG object = new GFG();

        // Calling show() method in main()
        object.show("Hello World!");

        // Print statement
        System.out.println(object.doSum(2, 3));
    }
}
```

**输出**

```
Hello World!
5
```