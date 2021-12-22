# Java 中自动装箱整数对象的比较

> 原文:[https://www . geesforgeks . org/comparison-autobox-integer-objects-Java/](https://www.geeksforgeeks.org/comparison-autoboxed-integer-objects-java/)

当我们给一个整数对象赋值时，该值被[自动装箱为一个整数对象。例如，语句“整数 x = 10”创建了一个值为 10 的对象“x”。](http://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)

以下是基于自动装箱整数对象比较的一些有趣的输出问题。

预测以下 Java 程序的输出

```java
// file name: Main.java
public class Main {
    public static void main(String args[]) {
         Integer x = 400, y = 400;
         if (x == y)
            System.out.println("Same");
         else
            System.out.println("Not Same");
    }
}
```

输出:

```java
Not Same
```

因为 x 和 y 指的是不同的对象，所以我们得到的输出是“不一样”

下面程序的输出是来自 Java 的一个惊喜。

```java
// file name: Main.java
public class Main {
    public static void main(String args[]) {
         Integer x = 40, y = 40;
         if (x == y)
            System.out.println("Same");
         else
            System.out.println("Not Same");
    }
}
```

输出:

```java
Same
```

在 Java 中，从-128 到 127 的值被缓存，因此返回相同的对象。如果值在-128 到 127 之间，则 valueOf()的实现使用缓存对象。

如果我们使用新的运算符显式创建整数对象，我们得到的输出是“不一样”。请参见下面的 Java 程序。在以下程序中，不使用 valueOf()。

```java
// file name: Main.java
public class Main {
    public static void main(String args[]) {
          Integer x = new Integer(40), y = new Integer(40);
         if (x == y)
            System.out.println("Same");
         else
            System.out.println("Not Same");
    }
}
```

输出:

```java
Not Same
```

预测以下程序的输出。这个例子是由*比沙尔·杜贝*提供的。

```java
class GFG
{
    public static void main(String[] args)
    {
    Integer X = new Integer(10);
    Integer Y = 10;

    // Due to auto-boxing, a new Wrapper object
    // is created which is pointed by Y
    System.out.println(X == Y);
    }
}
```

输出:

```java
false

```

**说明:**这里会创建两个对象。由于调用新操作符而被 X 指向的第一个对象和由于自动装箱而被创建的第二个对象。

本文由**阿沛·拉提**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。