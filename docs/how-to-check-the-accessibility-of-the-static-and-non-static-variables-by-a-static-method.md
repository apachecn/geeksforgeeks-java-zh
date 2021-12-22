# 如何用静态方法检查静态和非静态变量的可及性？

> 原文:[https://www . geesforgeks . org/如何通过静态方法检查静态和非静态变量的可访问性/](https://www.geeksforgeeks.org/how-to-check-the-accessibility-of-the-static-and-non-static-variables-by-a-static-method/)

[static](https://www.geeksforgeeks.org/static-keyword-java/) 关键字是 Java 中的非访问修饰符，可用于变量、方法和代码块。[静态变量](https://www.geeksforgeeks.org/static-variables-in-java-with-examples/)在 Java 中属于类，即它在执行开始时只初始化一次。通过使用静态变量，类的所有实例共享一个副本，它们可以通过类名直接访问，不需要任何实例。**静态方法**同样属于类而不是实例，它只能访问静态变量，不能访问非静态变量。

**例 1:** 静态方法可以访问静态变量。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to check accessibility
// of static variables inside
// static methods

class GFG {

    // declaring variable 'a' as static
    static int a = 5;

    // main is also a static type
    public static void main(String args[])
    {

        // accessing value of
        // static variable
        System.out.println("Static variable:" + a);
    }
}
```

**Output**

```java
Static variable:5
```