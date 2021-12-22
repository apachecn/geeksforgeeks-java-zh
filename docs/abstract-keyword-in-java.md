# Java 中的抽象关键字

> 原文:[https://www.geeksforgeeks.org/abstract-keyword-in-java/](https://www.geeksforgeeks.org/abstract-keyword-in-java/)

*抽象*是 java 中适用于类、方法的非访问修饰符，但**不是**变量。它用于实现抽象，这是面向对象编程的支柱之一。以下是在 Java 中可以使用*抽象*的不同上下文。

**[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)**

具有部分实现的类(即，不是类中存在的所有方法都有方法定义)。要声明类抽象，请使用以下通用形式:

```
abstract class class-name{
    //body of class
}

```

由于它们的部分实现，我们不能实例化抽象类。抽象类的任何子类必须实现超类中的所有抽象方法，或者声明为抽象的。java 中的一些预定义类是抽象的。它们依赖于它们的子类来提供完整的实现。比如 [java.lang.Number](https://www.geeksforgeeks.org/java-lang-number-class-java/) 就是一个抽象类。有关抽象类的更多信息，请参见 java 中的[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)

**抽象方法**

有时，我们只需要超类中的方法声明。这可以通过指定**抽象**类型修改器来实现。这些方法有时被称为*子类责任*，因为它们在超类中没有指定实现。因此，子类必须[覆盖](https://www.geeksforgeeks.org/overriding-in-java/)它们来提供方法定义。要声明抽象方法，请使用以下通用形式:

```
abstract type method-name(parameter-list);

```

如您所见，不存在方法体。任何扩展抽象类的具体类(即没有抽象关键字的类)都必须覆盖该类的所有抽象方法。

**抽象方法的重要规则:**

*   Any class containing one or more abstract methods must also be declared abstract.
*   The following are various **illegal combinations of other modifiers of the method** About *Abstract* Modifier:
    1.  finally
    2.  Abstract native
    3.  Abstract synchronous
    4.  Abstract static
    5.  Private [T21 T22] abstract and strict [T23

考虑下面的 java 程序，它说明了类和方法使用*抽象*关键字。

```
// A java program to demonstrate 
// use of abstract keyword.

// abstract with class
abstract class A 
{
    // abstract with method
    // it has no body
    abstract void m1();

    // concrete methods are still allowed in abstract classes
    void m2()
    {
        System.out.println("This is a concrete method.");
    }
}

// concrete class B
class B extends A 
{
    // class B must override m1() method
    // otherwise, compile-time exception will be thrown
    void m1() {
        System.out.println("B's implementation of m2.");
    }

}

// Driver class
public class AbstractDemo 
{
    public static void main(String args[]) 
    {
        B b = new B();
        b.m1();
        b.m2();
    }
}
```

输出:

```
B's implementation of m2.
This is a concrete method.

```

**注意:**虽然抽象类不能用来实例化对象，但是可以用来创建对象引用，因为 Java 对[运行时多态](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/)的方法是通过使用超类引用来实现的。因此，必须能够创建对抽象类的引用，以便可以使用它来指向子类对象。

**摘要和[最终](https://www.geeksforgeeks.org/final-keyword-java/)T3】**

在 java 中，您永远不会看到一个类或方法同时声明了 [final](https://www.geeksforgeeks.org/final-keyword-java/) 和抽象关键字。对于类，final 用于防止[继承](https://www.geeksforgeeks.org/inheritance-in-java/)，而抽象类依赖于它们的子类来完成实现。在方法的情况下，final 用于防止[覆盖](https://www.geeksforgeeks.org/overriding-in-java/)，而抽象方法需要在子类中被覆盖。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。