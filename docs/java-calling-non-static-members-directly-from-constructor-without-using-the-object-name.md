# Java–不使用对象名直接从构造函数调用非静态成员

> 原文:[https://www . geesforgeks . org/Java-调用-非静态-成员-直接从构造函数-不使用对象名/](https://www.geeksforgeeks.org/java-calling-non-static-members-directly-from-constructor-without-using-the-object-name/)

Java 是一种面向对象编程语言。我们需要创建对象来访问类内的方法和变量。然而，这并不总是正确的。在讨论 java 中的静态关键字时，我们了解到静态成员是类级别的，无需任何实例就可以直接访问。这里我们将讨论如何在不使用对象名称的情况下访问[非静态数据成员](https://www.geeksforgeeks.org/difference-between-static-and-non-static-method-in-java/)，该对象名称让我们比较静态数据成员和非静态数据成员，如下表所示:

<figure class="table">

| **Static data member** | **Non-static data member** |
| --- | --- |
| They are declared with the keyword "static". | Each member in Java is a non-static one by default, and there is no "static" keyword in front of it. |
| All objects of a class share the same copy of static data members. | Each object of the class has its own non-static data member copy. |
| They can be accessed using class names or objects. | Generally accessed through the object of the class. |
| Static methods can be called without instances or objects of this class. | Non-static methods can access any static methods and static variables without creating instances of objects. |

</figure>

**示例 1:** 在没有该类的实例或对象的情况下调用静态数据成员。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program Illustrating Calling Static Data Members
// Without the Instance or object of that class

// Main class
public class GFG {

    // Static variable
    static int a = 5;

    // Method 1
    // Static method
    static void f()
    {
        // Print statement whenever static method is called
        System.out.println("I am static method");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Calling static data members without the
        // instance or object of that class.
        System.out.println(GFG.a);

        // Calling method 1
        GFG.f();
    }
}
```

**Output**

```
5
I am static method
```