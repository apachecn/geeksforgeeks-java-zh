# Java 中的构造函数

> 原文:[https://www.geeksforgeeks.org/constructors-in-java/](https://www.geeksforgeeks.org/constructors-in-java/)

顾名思义，这是一个在我们的程序中用来构建某些东西的术语。所以基本上，如果我们想得更深，我们总是先声明变量，然后初始化它们。Java 是面向对象的语言，我们的目标是让代码更接近现实世界，在现实世界中我们创建对象，现在需要有人检查这些对象的结构，以了解它们在内部是如何工作的。

插图:

```java
Animal gorilla  = new Animal() ;
```

这里 gorilla 是一个对象，不能设置为 0 或 null，只是不太可能是 int、char、float 等，所以基本上我们需要根据需求初始化这些对象。这就产生了可以有多种类型的构造函数。

一些极客现在肯定在想，他们不知道这个概念，但他们仍然能够成功地运行程序。答案很简单，因为存在一个默认的构造函数，它有一个空的主体，如果没有编写构造函数，它总是被自动调用，这是在后端成功初始化对象的原因。现在，您一定想知道这个构造函数是否会自动调用自己，那么为什么需要多个构造函数。参考上面的例子，我们可以想象许多属性与它相关联，它不能用 0 或 null 初始化，因为这没有意义，因此我们知道为什么默认构造函数体是空的，并且仍然需要一些东西来初始化 java 中对象的属性。

现在，geek 继续前进，你一定想知道这个关键字，在它的帮助下，我们可以实现这个目标，但是当代码的可伸缩性增加时，在代码中出现重复行时，在每个需要的地方初始化对象的属性变得非常乏味。因此，很可能我们已经学会了在程序中重复使用一些重复工作时创建一个函数，同样，这里我们有一些构造函数，这些构造函数可以初始化并调用对象，只需在一些框内编写，我们将看到这是一种语法，其中这个块现在负责对象的初始化，无论对象有多少，在代码中的什么位置，因为相应的构造函数将在对象初始化后立即自动调用。现在让我们从技术上深入探讨这个概念。

**构造函数和 Java 中的方法有什么不同？**

*   构造函数必须与定义它的类同名，而对于 java 中的方法来说这是不必要的。
*   构造函数不返回任何类型，而方法具有返回类型，或者如果不返回任何值，则**无效**。
*   构造函数在对象创建时只被调用一次，而方法可以被调用任意多次。

现在让我们想出在创建对象或实例时调用的构造函数的语法。

```java
class Geek
{   
  .......

  // A Constructor
  new Geek() {}

  .......
}

// We can create an object of the above class
// using the below statement. This statement
// calls above constructor.
Geek obj = new Geek(); 
```

> **记住:**编写构造函数有一定的**规则如下:**
> 
> *   类的构造函数必须与其所在的类名同名。
> *   Java 中的构造函数不能是抽象的、最终的、静态的和同步的。
> *   在构造函数声明中可以使用访问修饰符来控制它的访问，即哪个类可以调用构造函数。

到目前为止，我们已经了解了构造函数用于初始化对象的状态。像[方法](https://www.geeksforgeeks.org/methods-in-java/)一样，构造函数也包含一组在对象创建时执行的语句(即指令)。

**建造师的需求？**

想象一个盒子。如果我们谈论一个盒子类，那么它会有一些类变量(比如长度、宽度和高度)。但是当涉及到创建它的对象时(即盒子现在将存在于计算机的内存中)，那么盒子是否可以没有为其尺寸定义的值。答案是否定的
所以构造函数用于在对象创建时给类变量赋值，要么由程序员显式完成，要么由 Java 本身(默认构造函数)完成。

**什么时候调用构造函数？**

每次使用 **new()** 关键字创建对象时，至少调用一个构造函数(可以是默认构造函数)来为同一类的**数据成员**分配初始值。现在是讨论构造函数类型的正确时机，因此在 java 中主要有两种类型的构造函数:

*   无参数构造函数
*   参数化构造函数

**类型 1:** 无参数构造函数

**无参数构造函数:**没有参数的构造函数称为默认构造函数。如果我们没有在类中定义构造函数，那么编译器会为类创建**默认构造函数(没有参数)**。如果我们编写一个有参数或者没有参数的构造函数，那么编译器不会创建一个默认的构造函数。

> 默认构造函数为对象提供默认值，如 0、null 等。取决于类型。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate calling a
// no-argument constructor
import java.io.*;

class Geek
{
    int num;
    String name;

    // this would be invoked while an object
    // of that class is created.
    Geek()
    {
        System.out.println("Constructor called");
    }
}

class GFG
{
    public static void main (String[] args)
    {
        // this would invoke default constructor.
        Geek geek1 = new Geek();

        // Default constructor provides the default
        // values to the object like 0, null
        System.out.println(geek1.name);
        System.out.println(geek1.num);
    }
}
```

**Output**

```java
Constructor called
null
0
```

**类型 2:** 参数化构造函数

具有参数的构造函数称为参数化构造函数。如果我们想用自己的值初始化类的字段，那么就使用参数化的构造函数。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Working of
// Parameterized Constructor

// Importing required inputoutput class
import java.io.*;

// Class 1
class Geek {
    // data members of the class.
    String name;
    int id;

    // Constructor would initialize data members
    // With the values of passed arguments while
    // Object of that class created
    Geek(String name, int id)
    {
        this.name = name;
        this.id = id;
    }
}

// Class 2
class GFG {
    // main driver method
    public static void main(String[] args)
    {
        // This would invoke the parameterized constructor.
        Geek geek1 = new Geek("adam", 1);
        System.out.println("GeekName :" + geek1.name
                           + " and GeekId :" + geek1.id);
    }
}
```

**Output**

```java
GeekName :adam and GeekId :1
```