# Java 中的协变返回类型

> 原文:[https://www.geeksforgeeks.org/covariant-return-types-java/](https://www.geeksforgeeks.org/covariant-return-types-java/)

当耳朵“覆盖”耳膜时，我们很快就知道这可以通过不同的数据类型或传递给函数的参数来实现，这是程序员在 java 中学习[多态性时最初学到的。](https://www.geeksforgeeks.org/polymorphism-in-java/)在 JDK 5.0 之前，[不可能通过改变返回类型来覆盖](https://www.geeksforgeeks.org/overriding-in-java/)方法。当我们重写父类方法时，子类中重写方法的名称、参数类型和返回类型必须与父类方法完全相同。覆盖方法被认为是关于返回类型的**不变量**。

从 Java 版本开始，子类中的重写方法可以有不同的返回类型，但是子类的返回类型应该是父类返回类型的子类型。关于返回类型，覆盖方法变为**变量**。

同变返回类型基于[李斯科夫替换原则](https://en.wikipedia.org/wiki/Liskov_substitution_principle)。

现在，极客们，你们一定想知道为什么要使用它，我们将列出它的优点如下:

*   它有助于避免混淆类层次结构中的类型转换，从而使代码可读、可用和可维护。
*   当重写方法时，我们可以拥有更具体的返回类型。
*   有助于防止返回时出现运行时 ClassCastExceptions

> **注意:**如果我们交换 Base 和 Derived 的返回类型，那么上面的程序将不起作用。请看[这个](https://ide.geeksforgeeks.org/mqAFFv)程序举例。

**示例**两个类用于返回类型

## Java

```
// Java Program to Demonstrate Different Return Types
// if Return Type in Overridden method is Sub-type

// Class 1
class A {
}

// Class 2
class B extends A {
}

// Class 3
// Helper class (Base class)
class Base {

    // Method of this class of class1 return type
    A fun()
    {
        // Display message only
        System.out.println("Base fun()");

        return new A();
    }
}

// Class 4
// Helper class extending above class
class Derived extends Base {

    // Method of this class of class1 return type
    B fun()
    {
        // Display message only
        System.out.println("Derived fun()");

        return new B();
    }
}

// Class 5
// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating object of class3 type
        Base base = new Base();

        // Calling method fun() over this object
        // inside main() method
        base.fun();

        // Creating object of class4 type
        Derived derived = new Derived();

        // Again calling method fun() over this object
        // inside main() method
        derived.fun();
    }
}
```

**输出:**

```
Base fun()
Derived fun()
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。