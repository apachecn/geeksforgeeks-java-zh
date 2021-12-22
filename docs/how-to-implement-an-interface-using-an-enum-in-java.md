# 如何在 Java 中使用枚举实现接口

> 原文:[https://www . geesforgeks . org/如何使用 java 中的枚举实现接口/](https://www.geeksforgeeks.org/how-to-implement-an-interface-using-an-enum-in-java/)

[枚举](https://www.geeksforgeeks.org/enum-in-java/)用于在编程语言中表示一组命名常数。例如，一副扑克牌中的 4 套花色可能是 4 个名为 Club、Diamond、Heart 和 Spade 的枚举数，属于名为花色的枚举类型。我们已经讨论了枚举的基础知识，它是如何在[之前的文章](https://www.geeksforgeeks.org/enum-in-java/)中声明的。在本文中，我们将了解枚举如何实现接口。

当一个方法参数只能从一个小的可能值集合中取值时，我们主要使用枚举，这意味着输入值是固定的，它从那个固定的值集合中取值。java enum 类型是一种特殊的 Java 类，它可以像普通的 Java 类一样包含常量和[方法](https://www.geeksforgeeks.org/methods-in-java/)，其中值是这个类唯一可能的实例。这个枚举扩展了[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/) **java.lang.Enum.** 考虑这样一种情况，当我们必须实现一些与给定[对象或类](https://www.geeksforgeeks.org/classes-objects-java/)的区别属性紧密耦合的业务逻辑时，我们实现了一个与枚举的接口。想象一个案例，我们需要将两个枚举的值合并成一个组，并以类似的方式对待它们，在那里*枚举实现了接口*。

因为枚举是隐式扩展抽象类 *java.lang.Enum* ，所以它不能扩展任何其他类或枚举，任何类也不能扩展枚举。所以很明显 enum 不能扩展或者不能扩展。但是当需要实现多重继承时，枚举可以实现任何接口，而在 java 中，有可能一个枚举可以实现一个[接口](https://www.geeksforgeeks.org/interfaces-in-java/)。因此，为了实现可扩展性，需要遵循以下步骤:

1.  创建[界面](https://www.geeksforgeeks.org/interfaces-in-java/)。
2.  创建接口后，通过枚举实现该接口。

下面是演示枚举中接口实现的代码:

```java
// Java program to demonstrate
// how an enum implements an
// interface

// Defining an interface
interface week {

    // Defining an abstract method
    public int day();
}

// Initializing an enum which
// implements the above interface
enum Day implements week {

    // Initializing the possible
    // days
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday,
    Sunday;

    public int day()
    {
        return ordinal() + 1;
    }
}

// Main Class
public class Daycount {
    public static void main(String args[])
    {
        System.out.println("It is day number "
                           + Day.Wednesday.day()
                           + " of a week.");
    }
}
```

**Output:**

```java
It is day number 3 of a week.

```