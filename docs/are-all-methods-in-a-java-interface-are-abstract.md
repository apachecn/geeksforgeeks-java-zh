# Java 接口中的所有方法都是抽象的吗？

> 原文:[https://www . geesforgeks . org/are-all-methods-in-a-Java-interface-are-abstract/](https://www.geeksforgeeks.org/are-all-methods-in-a-java-interface-are-abstract/)

在 java 中，接口被称为类的蓝图，它用于实现 Java 中的抽象。通过只使用接口，我们可以在 java 中实现多重继承。

*   让我们通过一个例子来理解蓝图的概念，比如建筑物的蓝图将由建筑物的属性和行为组成，但是对于每个建筑物来说，它可能是不同的，类似于这些接口有抽象的方法，当由类实现时，它们将有自己独特的行为。
*   当实现一个接口时，我们强制这个类实现它的方法，如果它没有实现它，那么我们需要声明这个类是抽象的。我们可以在接口中有默认的和静态的方法。
*   Java 8 引入了默认方法的概念，之所以在 Java 8 中添加它们，是因为在某个场景中，接口使用起来不舒服。例如，如果我们有一个由许多类实现的方法，并且在每种情况下功能都是相同的，那么对于相同的功能，我们需要在每个类中一次又一次地编写这个函数，因此为了消除这个困难，给出了 Java 8 中的默认方法。
*   默认情况下，所有方法都是公共的和抽象的，直到我们不将其声明为默认值，并且属性是静态的和最终的。

**一个 Java 接口中的所有方法都是抽象的！**

抽象方法没有主体，它们只有声明，没有定义。定义是通过实现类来定义的。所以我们看一下所有的例子，在这些例子中，一个方法可以存在，它的行为(主体)在接口内部。现在我们将尝试在接口内部的不同场景中赋予方法主体。

**例 1:**

*   在这个例子中，我们将有一个抽象方法 heightDisplay()(没有主体)，它将由类 GFG 实现。
*   所以 GFG 类需要实现 heightDisplay()方法，为了调用这个方法，我们将创建 GFG 类的对象。
*   所以我们的第一个例子告诉我们，我们可以在接口中有抽象方法，我们这样做只是为了证明接口只包含抽象方法。

下面是接口中只有一个抽象方法的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
interface Building {
    // abstract methods
    void heightDisplay();
}

class GFG implements Building {
    // implementing the abstract method
    // of building interface
    public void heightDisplay()
    {
        System.out.println("height is 5");
    }
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.heightDisplay();
    }
}
```

**Output**

```
height is 5
```

**例 2 :**

*   在这个例子中，我们将有一个实例方法 widthDisplay()，它也将有它的主体。在身体内部，我们将打印一份声明。
*   现在我们知道接口只由抽象方法组成，所以当我们运行它时，我们会得到错误。将有 3 个错误，但第一个错误将出现在第 6 行**错误名称:** **接口抽象方法不能有主体。**
*   所以我们通过这个例子证明了在接口内部不能有实例方法。简单来说，实例方法是非静态的方法。实例方法将为不同的方法产生不同的输出，因为不同的对象具有不同的实例属性，实例方法在这些属性上工作。
*   所以这个例子也支持接口只能由抽象方法组成的说法。

下面是接口中有一个实例方法和一个抽象方法的示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
interface Building {
    // abstract methods
    void heightDisplay();

    // instance method with body
    void widthDisplay()
    {
        System.out.pritnln("width is 1");
    }
}

class GFG implements Building {
    // implementing the abstract method
    // of Building interface
    public void heightDisplay()
    {
        System.out.println("height is 5");
    }

    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.heightDisplay();
        gfg.widthDisplay();
    }
}
```

**输出**

```
prog.java:10: error: interface abstract methods cannot have body
    {
    ^
prog.java:15: error: GFG is not abstract and does not override abstract method widthDisplay() in Building
class GFG implements Building {
^
prog.java:27: error: cannot find symbol
        gfg.widthDisplay();
           ^
  symbol:   method widthDisplay()
  location: variable gfg of type GFG
3 errors
```

**例 3:**

*   在本例中，我们将使用最后一个方法 widthDisplay()，它将在其主体中打印宽度。因此，我们用它的主体定义了最后一个方法。
*   这违反了抽象方法的接口规则，因为它只有一个方法体。
*   有一点需要注意的是，我们不能用抽象的方法来使用最终的关键字，所以这也给了我们关键字非法组合的错误。但是我们没有用抽象的关键字比我们怎么能得到非法组合的错误。因为默认情况下，所有方法在接口内部都是抽象的。
*   所以这个例子说明了我们不能在接口中有最终的方法。因此，这个例子也表明我们只能在接口内部使用抽象方法。

下面是接口中有一个 final 和一个抽象方法的例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
interface Building {
    // abstract methods
    void heightDisplay();

    // final methods
    final void widthDisplay()
    {
        System.out.pritnln("width is 1");
    }
}

class GFG implements Building {
    public void heightDisplay()
    {
        System.out.println("height is 5");
    }
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.heightDisplay();
    }
}
```

**输出**

```
prog.java:9: error: modifier final not allowed here
    final void widthDisplay()
               ^
prog.java:10: error: interface abstract methods cannot have body
    {
    ^
prog.java:15: error: GFG is not abstract and does not override abstract method widthDisplay() in Building
class GFG implements Building {
^
3 error
```

**例 4:**

*   在这个例子中，我们将有一个抽象方法 widthDisplay()，它的主体在接口内部。如你所知抽象方法不能有身体所以它也会给我们错误其中一个错误将是**抽象方法不能有** **身体。**
*   所以在这个例子中，我们试图给抽象方法赋予主体，即使我们知道抽象方法不能有主体，只是为了证明我们只能在接口内部有抽象方法。
*   所以这个例子也支持我们的声明，接口只能由抽象方法组成。

下面是一个抽象方法的例子，它的主体在接口内部:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
interface Building {
    // abstract method
    void heightDisplay();

    // giving body to abstract method
    abstract void widthDisplay()
    {
        System.out.pritnln("width is 1");
    }
}

class GFG implements Building {
    public void heightDisplay()
    {
        System.out.println("height is 5");
    }
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.heightDisplay();
    }
}
```

**输出**

```
prog.java:10: error: interface abstract methods cannot have body
    {
    ^
prog.java:15: error: GFG is not abstract and does not override abstract method widthDisplay() in Building
class GFG implements Building {
^
2 errors
```

**注意:**在 Java 8 之前，我们在接口内部没有静态方法，但是现在我们可以在接口内部有静态方法。

**例 5:**

*   在 Java 8 之前，我们在接口内部没有静态方法，但是从 Java 8 开始，我们可以在接口内部有抽象方法。
*   但是在这个例子中，不会有错误。所以我们可以有一些方法，它们可以在接口中有自己的主体，其中一个是静态方法。
*   所以从 Java 8 开始，说接口只能有抽象方法并不是 100 %正确的。

下面是接口内部有一个静态方法的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
interface Building {
    // abstract method
    void heightDisplay();

    // static method
    static void widthDisplay()
    {
        System.out.println("width is 1");
    }
}

class GFG implements Building {
    // implementing tha abstract method
    // of Building interface
    public void heightDisplay()
    {
        System.out.println("height is 5");
    }
    public static void main(String[] args)
    {

        GFG gfg = new GFG();
        gfg.heightDisplay();
        // accessing the static method
        // by using of interface name
        Building.widthDisplay();
    }
}
```

**Output**

```
height is 5
width is 1
```

**例 6 :**

*   在 Java 8 中，我们还可以使用默认方法。默认方法允许接口具有不需要由实现该接口的类实现的方法。
*   默认方法最适合的一个例子，假设您有一个接口方法被许多类使用，并且所有类的功能都是相同的，在这种情况下，您需要在每个类中实现，即使每个类的主体都是相同的。所以 Java 8 引入了默认方法的概念来克服这种情况。
*   因此，我们可以说我们可以在接口中有**静态**和**默认**方法，除此之外我们只有抽象方法。

下面是在接口中使用默认方法的示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
interface Building {
    // abstract methods
    void heightDisplay();

    // default method
    default void widthDisplay()
    {
        System.out.println("width is 1");
    }
}

class GFG implements Building {
    // implementing abstract method
    // of Building interface
    public void heightDisplay()
    {
        System.out.println("height is 5");
    }
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.heightDisplay();

        // calling default method
        gfg.widthDisplay();
    }
}
```

**Output**

```
height is 5
width is 1
```