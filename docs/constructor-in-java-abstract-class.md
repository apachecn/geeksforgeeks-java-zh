# Java 抽象类中的构造函数

> 原文:[https://www . geesforgeks . org/constructor-in-Java-abstract-class/](https://www.geeksforgeeks.org/constructor-in-java-abstract-class/)

**构造函数**在类本身中总是通过类名来调用。构造函数用于初始化对象，而不是构建对象。众所周知，抽象类也有一个构造函数。因此，如果我们没有在抽象类中定义任何构造函数，那么 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) (Java 虚拟机)将为抽象类提供一个默认构造函数。如果我们想知道如何定义用户定义的构造函数，比如带参数的构造函数或者抽象类中的任何类型的构造函数，那么您应该遵循给定的过程。

> **注意:**抽象类是用[抽象关键字](https://www.geeksforgeeks.org/abstract-keyword-in-java/)声明的类。

**T2 抽象类的属性:**

*   抽象可以有抽象方法和非抽象方法。
*   它必须用抽象关键字声明。
*   它可以有一个构造函数，静态方法。
*   它可以有一个最终方法，防止抽象类的子类不改变方法的主体
*   抽象方法包含无体或者简单的说，你可以说你不能在抽象类里面定义一个抽象方法。我们可以在其抽象类的派生类中定义一个抽象方法。
*   抽象类的对象不能被实例化它意味着你不能直接创建一个抽象类对象，但是你可以通过引用它的子类来创建它的对象。

**程序:**

*   如果您在抽象类中用参数定义自己的构造函数，但是忘记在派生类构造函数中调用自己的构造函数，那么 JVM 将默认调用该构造函数。
*   因此，如果您在抽象类中定义了单参数或多参数构造函数，那么请确保使用 [super 关键字](https://www.geeksforgeeks.org/super-keyword/)调用驱动类构造函数中的构造函数。

**实现:**在这个程序中，我们将使用上面提到的方法将两个数字相乘。

**第一步:**我们创建一个名为*【内容】*的抽象类，定义一个用户定义一个带有一个参数的构造函数，一个名为*【a】*的变量，以及一个名为*【乘法】*的抽象方法

**步骤 2:** 我们创建一个类，这个类必须从这个名为“GFG”的抽象类“Content”派生。在 GFG 类中，我们将定义一个构造函数，在方法中使用 super 关键字调用父类构造函数，并在其中定义其父类的抽象方法。

**步骤 3:** 现在在我们的函数的主类中，也就是*“GeeksforGeeks”*这里，我们将通过引用其派生类对象来创建抽象类“Content”的对象。然后我们通过对象调用抽象类的方法。

**步骤 4:** 在方法内部，我们将存储在不同变量名中的值相乘，其中一个变量是抽象类的变量。我们可以通过抽象类的派生类对象来访问它的变量。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Concept of Constructors
// in Abstract Class

// Class 1
// Helper Abstract class
// Parent class
abstract class Content {

    int a;

    // Constructor of abstract class
    public Content(int a)
    {

        // This keyword refers to current instance itself
        this.a = a;
    }

    // Abstract method of abstract class
    abstract int multiply(int val);
}

// Class 2
// Helper class extending above Class1
// Child class of Abstract class
class GFG extends Content {

    // Constructor of Child class GFG
    GFG()
    {

        // Super keyword refers to parent class
        super(2);
    }

    // Defining method the abstract method
    public int multiply(int val)
    {

        // Returning value of same instance
        return this.a * val;
    }
}

// Class 3
// Main class
public class GeeksforGeeks {

    // Main driver method
    public static void main(String args[])
    {

        // Creating reference object of abstract class
        // using it child class
        Content c = new GFG();

        // Calling abstract method of abstract class
        System.out.println(c.multiply(3));
    }
}
```

**Output**

```
6
```