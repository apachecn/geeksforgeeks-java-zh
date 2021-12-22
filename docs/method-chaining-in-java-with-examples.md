# Java 中的方法链接示例

> 原文:[https://www . geesforgeks . org/method-chaining-in-Java-with-examples/](https://www.geeksforgeeks.org/method-chaining-in-java-with-examples/)

**方法链接**是在一行中调用不同的[方法](https://www.geeksforgeeks.org/methods-in-java/)的做法，而不是单独调用其他具有相同对象引用的方法。在这个过程中，我们必须写一次对象引用，然后通过用点分隔来调用方法。).

Java 中的方法链接是在 OOPs 中调用多个方法调用的常见语法。链接中的每个方法都返回一个对象。它违反了对中间变量的需求。换句话说，方法链接可以被定义为如果我们有一个对象，并且我们在那个对象上一个接一个地调用方法，这被称为方法链接。

**语法:**

```
obj.method1().method2().method3();  
```

在上面的语句中，我们有一个对象(obj)并调用 method1()，然后调用 method2()，之后调用 method3()。因此，一个接一个地调用方法被称为方法链接。

> **注:**Java 中的方法链接也称为参数习惯用法或命名参数习惯用法。有时它也被称为火车残骸，因为方法数量的增加，即使方法之间经常添加换行符。

我们先来审核一下这个例子，然后解释起来会顺畅很多。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class A {

    private int a;
    private float b;

    A() { System.out.println("Calling The Constructor"); }

    int setint(int a)
    {
        this.a = a;
        return this.a;
    }

    float setfloat(float b)
    {
        this.b = b;
        return this.b;
    }

    void display()
    {
        System.out.println("Display=" + a + " " + b);
    }
}

// Driver code
public class Example {
    public static void main(String[] args)
    {
        // This will return an error as
        // display() method needs an object but
        // setint(10) is returning an int value
        // instead of an object reference
        new A().setint(10).display();
    }
}
```

**Java 代码编译错误:**

```
prog.java:34: error: int cannot be dereferenced
        new A().setint(10).display();
                          ^
1 error
```

**说明:**

*   当我们调用构造函数时，我们应该意识到构造函数不包含任何返回类型，但是它返回当前的对象引用。[打开此](https://www.geeksforgeeks.org/constructors-in-java/)了解更多关于构造函数的信息。
*   由于对象引用是由构造函数返回的，我们也可以使用返回的对象引用来调用另一个方法。
*   因此，通过实现点(。)运算符，我们也可以调用另一个名为“setint(10)”的方法。到目前为止，我们正在尝试进一步调用显示方法，但是，这是不可能的。为什么呢？看看下一点。
*   现在，“setint(10)”方法返回变量的整数值。一般来说，人们很容易理解下一个方法不能基于一个变量来调用。为了解决这个问题，“setint(10)”方法必须返回对象引用。怎么做？。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class A {

    private int a;
    private float b;

    A() { System.out.println("Calling The Constructor"); }

    public A setint(int a)
    {
        this.a = a;
        return this;
    }

    public A setfloat(float b)
    {
        this.b = b;
        return this;
    }

    void display()
    {
        System.out.println("Display=" + a + " " + b);
    }
}

// Driver code
public class Example {
    public static void main(String[] args)
    {
        // This is the "method chaining".
        new A().setint(10).setfloat(20).display();
    }
}
```

**Output**

```
Calling The Constructor
Display=10 20.0
```

*   在上面的例子中，我们已经导出了 setint(int a)和 setfloat(float b)方法作为类类型。
*   在这种情况下，在返回时，我们使用“this”，它返回当前实例引用。检查[本](https://www.geeksforgeeks.org/this-reference-in-java/)中“本”参考变量的用途和值。
*   当在主方法中实现方法链接时，“setint(10)”&“setfloat(20)”正在返回对象的引用，该引用进一步用于调用“display()”方法。