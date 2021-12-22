# Java 错误–方法的所有非法修饰符组合

> 原文:[https://www . geesforgeks . org/Java-error-all-invalid-修饰符-组合-for-methods-w-r-t-abstract/](https://www.geeksforgeeks.org/java-error-all-illegal-modifier-combinations-for-methods-w-r-t-abstract/)

在 Java 中，我们可以对类、方法、块和变量应用各种各样的[修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)，每一个都有不同的用例，所有这些主要定义了这些类、方法、块和变量如何以及在哪里被访问和修改。但是并不是所有的修饰语都可以同时使用，因为它们的定义和这些修饰语能让我们做什么之间有些矛盾。因此，不能同时应用的修饰符组合形成了一个非法的修饰符组合，无论我们在哪里使用，我们都会得到编译时错误。

**例如–**声明为*公共*的方法可以从程序中的任何地方访问，但是*私有*方法只能在声明它的类中访问。因此，如果我们试图对一个方法应用公共和私有修饰符，它将形成一个非法的修饰符组合，并给出如下所示的编译时错误。

## Java

```java
// Java program to illustrate
// illegal modifier combination

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        System.out.println("GFG!");
    }

    // the below method has illegal modifier combination
    protected public void m1() {}
}
```

上面的代码抛出编译时错误如下:

```java
GFG.java:13: error: illegal combination of modifiers: public and protected
   protected public void m1() {}
                         ^
1 error
```

现在，在理解不同的非法修饰语组合之前，我们先来理解一下*抽象的*关键词。

在 Java 中，*抽象*是适用于类和方法但不适用于变量的修饰符，它帮助我们在 Java 中实现[抽象](https://www.geeksforgeeks.org/abstraction-in-java-2/)。抽象是一种我们只公开我们提供的服务，而隐藏内部细节和实现的方式。

让我们了解一下抽象方法和抽象类:

### 抽象方法

即使我们不知道实现，我们仍然可以用*抽象*修饰符编写一个方法，也就是说，唯一的声明是可用的，但是没有实现。因此，抽象方法不应该有任何人，应该以分号结束。因此，扩展抽象类的每个类都必须实现所有的抽象方法，或者应该声明为抽象的。

下面给出一个演示抽象方法的例子:

## Java

```java
// Java program to illustrate
// Abstract method

// Importing required packages
import java.util.*;

// Declaring an abstract class
abstract class Animal {

    // Declaring an abstract method
    public abstract String getSound();
}

// Declaring a class Cat by extending
// the above Animal class
class Cat extends Animal {

    // Implementing the above
    // anstract method of animal class
    public String getSound() { return "Meow!"; }

    // main method
    public static void main(String[] args)
    {

        // Creating an object of type class Cat
        Cat c = new Cat();

        // Calling getSound method
        System.out.println(c.getSound());
    }
}
```

**Output**

```java
Meow!
```

### **抽象类**

抽象类是我们不能实例化对象的类，它基本上定义并提供了派生类的蓝图，以及具体类在继承抽象类时必须实现的方法。

任何作为继承它的类的一般化的类都可以被声明为抽象的。例如，动物类是对各种动物的概括。所有的动物都有一些共同的属性，但是有不同的价值和实现。因此，动物类可能看起来像这样:

```java
abstract class Animal {

    public abstract String getSound();

    public abstract String getColour();

    public abstract move();

    // Many more methods follow...

}
```

现在，在学习 w.r.t 抽象的所有非法修饰语组合之前，这里有一个快速的建议:

> **注:**由于抽象从不谈论实现，任何与实现有关的修饰语都与抽象形成非法组合。另外，抽象关键字促进了[遗传](https://www.geeksforgeeks.org/inheritance-in-java/)和[多态性](https://www.geeksforgeeks.org/polymorphism-in-java/)，因此，任何限制遗传或多态性的修饰语也形成了非法组合。这些可以用作经验法则，同时识别那些与抽象构成非法组合的修饰语。

### Java 中方法抽象的所有非法修饰符组合

以下是 w.r.t 方法的修饰符的各种非法组合

#### **1。最终摘要**

*   **编译时错误:**修饰符的非法组合:“final”和“abstract”
*   **原因:**抽象方法必须在子类中被覆盖才能提供实现，而最终方法不能被覆盖。所以，这是一种非法组合。
*   **解析:**我们既可以只将方法声明为 final，这将限制在子类中重写方法，也可以只将其声明为抽象的，并根据需要在子类中实现该方法。

#### **2。原生摘要**

*   **编译时错误:**修饰符的非法组合:“本机”和“抽象”
*   **原因:**对于原生方法，其他一些语言(C 或 C++)中已经存在实现，但是对于抽象方法，不应该存在实现。所以，它也形成了一个非法组合。
*   **解析:**我们只能在其他语言中已经有实现的情况下使用 native，或者将方法保持为抽象的。

#### **3。私人摘要**

*   **编译时错误:**修饰符的非法组合:“私有”和“抽象”
*   **原因:**抽象方法应该对子类可用以提供实现，而私有方法对子类不可用，因此这是一种非法的组合。
*   **解析:**如果方法在子类中不是必需的，并且只被定义它的类使用，那么用 private only 声明它，或者声明它为抽象的并在子类中实现。

#### **4。静态摘要**

*   **编译时错误:**修饰符的非法组合:“静态”和“抽象”
*   **原因:**抽象方法必须在子类中被覆盖才能提供实现，而静态方法不能被覆盖(静态方法可以被隐藏，但这与覆盖有本质区别)。
*   **解析:**如果希望方法由子类实现，那么保持它的抽象性，或者只在不允许重写的情况下声明为静态。

#### **5。Strictfp 摘要**

*   **编译时错误:**修饰符的非法组合:“strictfp”和“abstract”
*   **原因:**如果一个方法被声明为 strictfp，那么它确保所有浮点计算都应该遵循 IEEE 754 标准，并将给出与平台无关的结果。所以基本上，它谈论的是实现，因此形成了与抽象的非法结合。
*   **解析:**要么只声明为抽象，要么声明为 strictfp，以确保平台无关的浮点计算。

#### **6。同步摘要**

*   **编译时错误:**修饰符的非法组合:“同步”和“抽象”
*   **原因:**为了防止多个线程在给定对象上同时执行一个方法，synchronized 关键字用于防止不一致问题。因此，当我们同步一个方法时，这意味着我们正在同步其中的代码。因此，实施是必要的。因此，这种组合也是违法的。
*   **解析:**如果线程安全很重要，要么只将方法声明为抽象的，要么保持同步。