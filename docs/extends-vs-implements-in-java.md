# 在 Java 中扩展 vs 实现

> 原文:[https://www . geesforgeks . org/extends-vs-implements-in-Java/](https://www.geeksforgeeks.org/extends-vs-implements-in-java/)

[继承](https://www.geeksforgeeks.org/inheritance-in-Java/)是 [OOP(面向对象编程)](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-Java/)的重要支柱。这是 Java 中允许一个类继承另一个类的特性(字段和方法)的机制。主要有两个关键词，**“扩展”**和**“实现”**在 Java 中是用来继承的。本文讨论了扩展和实现之间的区别。

在讨论差异之前，让我们先了解每个关键词在哪些场景中使用。

**Extends:** 在 Java 中， *extends* 关键字用来表示正在定义的[类](https://www.geeksforgeeks.org/classes-objects-Java/)是使用继承从基类派生出来的。所以基本上，extends 关键字用于将父类的功能扩展到子类。在 Java 中，由于模糊性，不允许多重继承。因此，一个类只能扩展一个类，以避免歧义。

**示例:**

```java
class One {
    public void methodOne()
    {

        // Some Functionality
    }
}

class Two extends One {

    public static void main(String args[])
    {
        Two t = new Two();

        // Calls the method one
        // of the above class
        t.methodOne();
    }
}
```

**实现:**在 Java 中，*实现*关键字用于实现一个[接口](https://www.geeksforgeeks.org/interfaces-in-Java/)。接口是一种特殊类型的类，它实现了完整的抽象，并且只包含[抽象方法](https://www.geeksforgeeks.org/abstract-methods-in-Java-with-examples/)。要访问接口方法，接口必须由具有 implements 关键字的另一个类“实现”，并且方法需要在继承接口属性的类中实现。由于接口没有方法的实现，一个类一次可以实现任意数量的接口。

**例**

```java
// Defining an interface
interface One {
    public void methodOne();
}

// Defining the second interface
interface Two {
    public void methodTwo();
}

// Implementing the two interfaces
class Three implements One, Two {
    public void methodOne()
    {

        // Implementation of the method
    }

    public void methodTwo()
    {

        // Implementation of the method
    }
}
```

**注意:**一个类可以扩展一个类，可以同时实现任意数量的接口。

**例**

```java
// Defining the interface
interface One {

    // Abstract method
    void methodOne();
}

// Defining a class
class Two {

    // Defining a method
    public void methodTwo()
    {
    }
}

// Class which extends the class Two
// and implements the interface One
class Three extends Two implements One {

    public void methodOne()
    {

        // Implementation of the method
    }
}
```

**注意:**一个接口一次可以扩展任意数量的接口。

**示例:**

```java
// Defining the interface One
interface One {
    void methodOne();
}

// Defining the interface Two
interface Two {
    void methodTwo();
}

// Interface extending both the
// defined interfaces
interface Three extends One, Two {
}
```

下表解释了扩展和接口之间的区别:

| 没有。 | 延伸 | 工具 |
| --- | --- | --- |
| 1. | 通过使用“extends”关键字，一个类可以继承另一个类，或者一个接口可以继承其他接口 | 通过使用“implements”关键字，类可以实现一个接口 |
| 2. | 扩展超类的子类覆盖超类中的所有方法并不是强制性的。 | 实现接口的类必须实现该接口的所有方法，这是强制性的。 |
| 3. | 一个类只能扩展一个超类。 | 一个类一次可以实现任意数量的接口 |
| 4. | 接口可以扩展任意数量的接口。 | 一个接口永远不能实现任何其他接口 |