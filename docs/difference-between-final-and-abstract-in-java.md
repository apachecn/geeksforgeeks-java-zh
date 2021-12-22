# Java 中 Final 和 Abstract 的区别

> 原文:[https://www . geesforgeks . org/Java 中最终与抽象的区别/](https://www.geeksforgeeks.org/difference-between-final-and-abstract-in-java/)

本文讨论了抽象类和最终类的区别。在讨论这些差异之前，让我们先了解每一个差异意味着什么。

**最终类:**用“最终”关键字声明的类称为最终类。final 关键字用于最终确定该类中使用的类、方法和变量的实现。使用 final 类的主要目的是防止类被继承(即)如果一个类被标记为 final，那么没有其他类可以从 final 类继承任何属性或方法。如果最后一个类被扩展，Java 会给出一个编译时错误。

下面是如何声明最终类的示例。但是，会出现编译时错误，因为这个最终类是被继承的。

```java
// Java program to demonstrate the
// Final class
final class Super {
    private int data = 100;
}
public class Sub extends Super {
    public static void main(String args[])
    {
    }
}
```

**抽象类:**使用“抽象”关键字声明的类称为抽象类。抽象类背后的主要思想是实现[抽象](https://www.geeksforgeeks.org/abstraction-in-java-2/)的概念。抽象类既可以有抽象方法(不带主体的方法)，也可以有具体方法(带主体的常规方法)。但是，普通类(非抽象类)不能有抽象方法。

下面是如何声明抽象类的示例。

```java
// Java program to demonstrate
// an abstract class

// Abstract parent class
abstract class Book {

    // Abstract method without body
    public abstract void page();
}

// shayar class extends Book class
public class shayar extends Book {

    // Declaring the abstract method
    public void page()
    {
        System.out.println("Geek");
    }

    // Driver code
    public static void main(String args[])
    {
        Book obj = new shayar();
        obj.page();
    }
}
```

上面的程序给出了“极客”作为输出。所有抽象方法都应该在子类中被重写，以提供实现。然而，从定义来看，最终的方法不能被覆盖。因此，抽象的最终组合对于方法来说是非法的。此外，对于抽象类，我们需要创建一个子类来提供实现，而对于最终类，我们不能创建子类。因此，对于类来说，最终的抽象组合是非法的。因此，最终类不能包含抽象方法，而抽象类可以包含最终方法。

下面是一个示例，演示了抽象类和最终类的组合。

```java
final class A {
    public abstract void methodOne();
}
```

显然，这个实现是无效的，因为最终类不能有抽象方法。作为最后一类是不能继承的。

```java
abstract class A {
    public final void methodOne() {}
}
```

但是，抽象类可以有最终方法。这个最终的方法被当作一个普通的方法，它的主体不能被覆盖。

下表演示了抽象类和最终类之间的区别:

| 没有。 | 抽象类 | 期末班 |
| --- | --- | --- |
| 1. | 使用“抽象”关键词。 | 使用“最终”关键词。 |
| 2. | 这有助于实现抽象。 | 这有助于限制其他类访问其属性和方法。 |
| 3. | 为了以后使用，所有的抽象方法都应该被覆盖 | 由于最终类不能被继承，所以不会出现覆盖概念 |
| 4. | 一些方法可以实现，一些不能 | 所有的方法都应该有实现 |
| 5. | 无法创建不可变的对象(事实上，无法创建任何对象) | 可以创建不可变的对象(例如字符串类) |
| 6. | 抽象类方法的功能可以在子类中改变 | 最终类方法应该像其他类一样使用 |
| 7. | 可以遗传 | 无法继承 |
| 8. | 无法实例化 | 可以实例化 |