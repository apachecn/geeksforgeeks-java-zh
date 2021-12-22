# Java 中的空白决赛

> 原文:[https://www.geeksforgeeks.org/blank-final-in-java/](https://www.geeksforgeeks.org/blank-final-in-java/)

Java 中的最后一个变量只能赋值一次，我们可以在声明中赋值，也可以在以后赋值。

```java
    final int i = 10;
    i = 30; // Error because i is final.
```

Java 中的一个**空白最终**变量是一个[最终](https://www.geeksforgeeks.org/g-fact-48/)变量，在声明过程中没有初始化。下面是一个简单的空白期末的例子。

```java
    // A simple blank final example 
    final int i;
    i = 30;
```

**如何将值分配给对象的空白最终成员？**
值必须在构造函数中赋值。

```java
// A sample Java program to demonstrate use and
// working of blank final
class Test
{
    // We can initialize here, but if we
    // initialize here, then all objects get
    // the same value.  So we use blank final
    final int i;

    Test(int x)
    {
        // Since we have initialized above, we
        // must initialize i in constructor.
        // If we remove this line, we get compiler
        // error.
        i = x;
    }
}

// Driver Code
class Main
{
    public static void main(String args[])
    {
        Test t1 = new Test(10);
        System.out.println(t1.i);

        Test t2 = new Test(20);
        System.out.println(t2.i);
    }
}
```

**输出:**

```java
10
20

```

 ***如果我们在类中有多个构造函数或重载构造函数，那么必须在所有这些构造函数中初始化空白的最终变量。然而，构造函数链可以用来初始化空白的最终变量。*** 

```java
// A Java program to demonstrate that we can
// use constructor chaining to initialize
// final members
class Test
{
    final public int i;

    Test(int val)    {  this.i = val;  }

    Test()
    {
        // Calling Test(int val)
        this(10);
    }

    public static void main(String[] args)
    {
        Test t1 = new Test();
        System.out.println(t1.i);

        Test t2 = new Test(20);
        System.out.println(t2.i);
    }
}
```

**输出:**

```java
10
20
```

空白的最终变量用于创建不可变的对象(成员一旦初始化就不能改变的对象)。

本文由**希曼希·古普塔供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论