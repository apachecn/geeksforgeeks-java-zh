# 用 Java 创建对象的不同方式

> 原文:[https://www . geesforgeks . org/different-way-create-objects-Java/](https://www.geeksforgeeks.org/different-ways-create-objects-java/)

我们可以用几种方法在 java 中创建一个类的对象，因为我们都知道一个类提供了对象的蓝图，你可以从一个类创建一个对象。这个概念被低估了，有时被证明是有益的，因为这个概念被许多程序员绕过了，有时甚至问来自面试感知。

**方法:**

在 Java 中有许多不同的方法来创建对象。让我们稍后在讨论时列出它们，稍后在程序的帮助下单独说明内部工作，通过这些工作我们可以在 Java 中创建对象。

1.  Use new keywords
2.  Use new instance
3.  Use the clone () method
4.  Use deserialization
5.  Constructor class using new instance () method

让我们一个接一个地讨论它们，并通过为它们附加一个干净的 java 程序来实现它们。

**方法 1:** 使用新关键字

在 java 中使用 [new 关键字](https://www.geeksforgeeks.org/new-operator-java/)是创建对象最基本的方法。这是在 java 中创建对象的最常见方式。几乎 99%的对象都是这样创建的。通过使用这个方法，我们可以调用任何我们想要调用的构造函数(没有参数或参数化构造函数)。

**示例**

## Java

```java
// Java program to Illustrate Creation of Object
// Using new keyword

// Main class
class GFG {

    // Declaring and initializing string
    // Custom input string
    String name = "GeeksForGeeks";

    // Main driver method
    public static void main(String[] args)
    {
        // As usual and most generic used we will
        // be creating object of class inside main()
        // using new keyword
        GFG obj = new GFG();

        // Print and display the object
        System.out.println(obj.name);
    }
}
```

**输出**

```java
GeeksForGeeks
```

**方法二:** [**使用新实例**](https://www.geeksforgeeks.org/new-operator-vs-newinstance-method-java/)

如果我们知道类的名字&如果它有一个公共的默认构造函数，我们可以创建一个对象 **Class.forName** 。我们可以用它来创建类的对象。类。forName 实际上在 Java 中加载该类，但不创建任何对象。要创建类的对象，必须使用类的新实例方法。

**例**

## 爪哇

```java
// Java program to Illustrate Creation of Object
// Using new Instance

// Main class
class GFG {

    // Declaring and initializing string
    String name = "GeeksForGeeks";

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            Class cls = Class.forName("GFG");

            // Creating object of main class
            // using instance method
            GFG obj = (GFG)cls.newInstance();

            // Print and display
            System.out.println(obj.name);
        }

        // Catch block to handle the exceptions

        // Catch block 1
        // Handling ClassNotFound Exception
        catch (ClassNotFoundException e) {

            // Display the exception along with line number
            // using printStacktrace() method
            e.printStackTrace();
        }

        // Catch block 2
        // Handling InstantiationException
        catch (InstantiationException e) {

            e.printStackTrace();
        }

        // Catch block 2
        // Handling IllegalAccessException
        catch (IllegalAccessException e) {

            e.printStackTrace();
        }
    }
}
```