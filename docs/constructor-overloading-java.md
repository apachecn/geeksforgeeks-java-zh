# Java 中的构造函数重载

> 原文:[https://www.geeksforgeeks.org/constructor-overloading-java/](https://www.geeksforgeeks.org/constructor-overloading-java/)

先决条件–[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)、[Java 中的重载](https://www.geeksforgeeks.org/overloading-in-java/)

除了重载方法，我们还可以在 java 中重载构造函数。执行[新建](https://www.geeksforgeeks.org/new-operator-vs-newinstance-method-java/)时，根据指定的参数调用重载构造函数。

**什么时候需要构造函数重载？**

有时需要以不同的方式初始化对象。这可以使用构造函数重载来完成。例如，Thread 类有 8 种构造函数。如果我们不想指定关于线程的任何东西，那么我们可以简单地使用线程类的默认构造函数，但是如果我们需要指定线程名，那么我们可以用如下的字符串参数调用线程类的参数化构造函数:

```
Thread t= new Thread (" MyThread "); 

```

让我们举个例子来理解构造函数重载的必要性。考虑一个类 Box 的以下实现，其中只有一个构造函数接受三个参数。

```
// An example class to understand need of
// constructor overloading.
class Box
{
    double width, height,depth;

    // constructor used when all dimensions
    // specified
    Box(double w, double h, double d)
    {
        width = w;
        height = h;
        depth = d;
    }

    // compute and return volume
    double volume()
    {
        return width * height * depth;
    }
}

```

正如我们所看到的，Box()构造函数需要三个参数。这意味着 Box 对象的所有声明都必须向 Box()构造函数传递三个参数。例如，以下语句当前无效:

```
Box ob = new Box();

```

由于 Box()需要三个参数，所以不使用它们调用它是错误的。假设我们只是想要一个没有初始维度的 box 对象，或者想要通过只指定一个用于所有三个维度的值来初始化一个多维数据集。从 Box 类的上述实现中，我们无法获得这些选项。

初始化对象的不同方法的这些类型的问题可以通过构造函数重载来解决。下面是类 Box 的改进版本，带有构造函数重载。

```
// Java program to illustrate
// Constructor Overloading
class Box
{
    double width, height, depth;

    // constructor used when all dimensions
    // specified
    Box(double w, double h, double d)
    {
        width = w;
        height = h;
        depth = d;
    }

    // constructor used when no dimensions
    // specified
    Box()
    {
        width = height = depth = 0;
    }

    // constructor used when cube is created
    Box(double len)
    {
        width = height = depth = len;
    }

    // compute and return volume
    double volume()
    {
        return width * height * depth;
    }
}

// Driver code
public class Test
{
    public static void main(String args[])
    {
        // create boxes using the various
        // constructors
        Box mybox1 = new Box(10, 20, 15);
        Box mybox2 = new Box();
        Box mycube = new Box(7);

        double vol;

        // get volume of first box
        vol = mybox1.volume();
        System.out.println(" Volume of mybox1 is " + vol);

        // get volume of second box
        vol = mybox2.volume();
        System.out.println(" Volume of mybox2 is " + vol);

        // get volume of cube
        vol = mycube.volume();
        System.out.println(" Volume of mycube is " + vol);
    }
}
```

输出:

```
Volume of mybox1 is 3000.0
Volume of mybox2 is 0.0
Volume of mycube is 343.0

```

**在构造函数重载中使用此()**

[这个()引用](https://www.geeksforgeeks.org/this-reference-in-java/)可以在构造函数重载时使用，从参数化构造函数隐式调用默认构造函数。请注意，这个()应该是构造函数中的第一个语句。

```
// Java program to illustrate role of this() in
// Constructor Overloading
class Box
{
    double width, height, depth;
    int boxNo;

    // constructor used when all dimensions and
    // boxNo specified
    Box(double w, double h, double d, int num)
    {
        width = w;
        height = h;
        depth = d;
        boxNo = num;
    }

    // constructor used when no dimensions specified
    Box()
    {
        // an empty box
        width = height = depth = 0;
    }

    // constructor used when only boxNo specified
    Box(int num)
    {
        // this() is used for calling the default
        // constructor from parameterized constructor
        this();

        boxNo = num;
    }

    public static void main(String[] args)
    {
        // create box using only boxNo
        Box box1 = new Box(1);

        // getting initial width of box1
        System.out.println(box1.width);
    }
}
```

输出:

```
0.0

```

正如我们在上面的程序中所看到的，我们在对象创建过程中只使用箱号来调用 Box(int num)构造函数。通过在其中使用此()语句，默认构造函数(Box())被隐式调用，这将使用 0 初始化 Box 的维度。

**注意:**构造函数调用应该是构造函数体中的第一条语句。例如，以下片段无效并引发编译时错误。

```
Box(int num)
{
    boxNo = num;

    /* Constructor call must be the first
       statement in a constructor */
    this();  /*ERROR*/
}

```

**做构造函数重载要注意的要点:**

*   The constructor call must be the **first** statement of the constructor in Java.
*   If we have defined any parameterized constructors, the compiler will not create default constructors. Conversely, if we don't define any constructors, the compiler will create default constructors (also known as no-arg constructors) by default during compilation.
*   Recursive constructor calls are invalid in java.

**构造函数重载与方法重载**

严格来说，构造函数重载有点类似于方法重载。如果我们想要使用不同数量的参数来初始化一个对象的不同方式，那么当我们想要基于不同参数的方法的不同定义时，我们必须像方法重载一样进行构造函数重载。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。