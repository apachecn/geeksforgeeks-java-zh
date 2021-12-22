# 显示继承构造函数的 Java 程序默认调用父构造函数

> 原文:[https://www . geesforgeks . org/Java-程序到显示-继承-构造函数-调用-默认情况下的父构造函数/](https://www.geeksforgeeks.org/java-program-to-show-inherited-constructor-calls-parent-constructor-by-default/)

在 java 中，有一个非常重要的关键字叫做 [super()关键字在 java 中](https://www.geeksforgeeks.org/super-keyword/)被广泛使用，因为它是面向对象的，所以继承性开始发挥作用。因此，每当我们在子构造函数中使用 super 关键字时，它就会自己调用默认的父构造函数。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate Inherited constructor
// calls the parent constructor by default

// Class 1
// Main class
class GFG {
    public static void main(String[] a)
    {
        // Inherited constructor calling
        new child();
        new parent();
    }
}

// Class 2
// Parent class - Helper class
class parent {

    // Constructor of parent class
    parent()
    {
        System.out.println("I am parent class constructor");
    }
}

// Class 3
// Child class - Helper class
class child extends parent {

    // Constructor of child class
    child()
    {
        System.out.println("I am child class constructor");
    }
}
```

**Output**

```
I am parent class constructor
I am child class constructor
I am parent class constructor
```