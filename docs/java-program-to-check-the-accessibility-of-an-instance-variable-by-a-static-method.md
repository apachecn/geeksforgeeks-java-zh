# 通过静态方法检查实例变量可访问性的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-check-accessibility-of-instance-variable-by-static-method/](https://www.geeksforgeeks.org/java-program-to-check-the-accessibility-of-an-instance-variable-by-a-static-method/)

一个**静态方法**属于类而不是类的对象。它可以在不需要创建类实例的情况下被调用。它可以访问静态数据成员，并可以更改其值。

[static](https://www.geeksforgeeks.org/static-keyword-java/) 关键字是 Java 中的非访问修饰符，可用于变量、方法和代码块。[静态变量](https://www.geeksforgeeks.org/static-variables-in-java-with-examples/)在 Java 中属于类，即它在执行开始时只初始化一次。通过使用静态变量，类的所有实例共享一个副本，它们可以通过类名直接访问，不需要任何实例。**静态方法**同样属于类而不是实例，它只能访问静态变量，不能访问非静态变量。

我们不能在静态方法中访问非静态变量或[实例变量](https://www.geeksforgeeks.org/variables-in-java/)。因为一个[静态方法](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)可以被调用，即使类中没有对象被实例化。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Check the Accessibility
// of an Instance variable by a Static Method

import java.io.*;

class GFG {

    // Instance variable
    public int k = 10;

    public static void main(String[] args)
    {

        // try to access instance variable a
        // but it's give us error
        System.out.print("value of a is: " + k);
    }
}
```

**输出:**

```java
prog.java:16: error: non-static variable k cannot be referenced from a static context
        System.out.print("value of a is: " + k);
                                             ^
1 error
```

实例变量，顾名思义，我们需要一个类的实例。我们不能从静态方法直接访问实例变量。因此，要访问实例变量，我们必须有一个从中访问实例变量的类的实例。

**例 2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to check accessibility of
// instance variables by static method

import java.io.*;

class GFG {

    // instance variable
    public int k;

    // Constructor to set value to instance variable
    public GFG(int k) { this.k = k; }

    // set method for instance variable
    public void setK() { this.k = k; }

    // get method for instance variable
    public int getK() { return k; }

    public static void main(String[] args)
    {

        // Calling class GFG where instance variable is
        // present
        GFG gfg = new GFG(10);

        // now we got instance of instance variable class
        // with help of this class we access instance
        // variable
        System.out.print("Value of k is: " + gfg.getK());
    }
}
```

**Output**

```java
Value of k is: 10
```