# Java 中的抽象方法及示例

> 原文:[https://www . geesforgeks . org/abstract-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/abstract-methods-in-java-with-examples/)

有时，我们只需要超类中的方法声明。这可以通过指定 [**抽象**](https://www.geeksforgeeks.org/abstract-keyword-in-java/) 类型修改器来实现。这些方法有时被称为*子类责任*，因为它们在超类中没有指定实现。因此，子类必须[覆盖](https://www.geeksforgeeks.org/overriding-in-java/)它们来提供方法定义。要声明抽象方法，请使用以下通用形式:

```java
abstract type method-name(parameter-list);
```

如您所见，不存在方法体。任何扩展抽象类的具体类(即没有抽象关键字的类)都必须覆盖该类的所有抽象方法。
**抽象方法的重要规则:**

*   任何包含一个或多个抽象方法的类也必须声明为抽象的
*   以下是关于*抽象*修饰符的其他方法修饰符的各种**非法组合**:
    1.  最后的
    2.  抽象原生
    3.  抽象同步
    4.  抽象静态
    5.  抽象私有
    6.  抽象严格计划

考虑下面的 Java 程序，它用类和方法说明了*抽象*关键字的使用。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A java program to demonstrate
// use of abstract keyword.

// abstract class
abstract class A {
    // abstract method
    // it has no body
    abstract void m1();

    // concrete methods are still
    // allowed in abstract classes
    void m2()
    {
        System.out.println("This is "
                           + "a concrete method.");
    }
}

// concrete class B
class B extends A {
    // class B must override m1() method
    // otherwise, compile-time
    // exception will be thrown
    void m1()
    {
        System.out.println("B's "
                           + "implementation of m1.");
    }
}

// Driver class
public class AbstractDemo {
    public static void main(String args[])
    {
        B b = new B();
        b.m1();
        b.m2();
    }
}
```

**输出:**

```java
B's implementation of m1.
This is a concrete method.
```

**注意:**虽然抽象类不能用来实例化对象，但是可以用来创建对象引用，因为 Java 对[运行时多态](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/)的方法是通过使用超类引用来实现的。因此，必须能够创建对抽象类的引用，以便可以使用它来指向子类对象。