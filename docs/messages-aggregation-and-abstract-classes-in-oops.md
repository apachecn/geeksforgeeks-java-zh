# OOPS

中的消息、聚合和抽象类

> 原文:[https://www . geesforgeks . org/messages-aggregation-and-abstract-class-in-oops/](https://www.geeksforgeeks.org/messages-aggregation-and-abstract-classes-in-oops/)

[**面向对象编程系统(OOPS)**](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/?ref=rp) 是很多编程语言的基本概念。它是基于包含方法和数据的对象的范例。这个概念被用来使编程成为一个行为像真实世界场景的类和对象模型。在本文中，我们将学习 OOPS 范例中的消息、聚合、组合和抽象类。

**[消息传递](https://www.geeksforgeeks.org/message-passing-in-java/) :** 就计算机而言，消息传递是进程之间的通信。它是面向对象编程和并行编程中使用的一种通信形式。Java 中的消息传递就像发送一个对象，即从一个线程到另一个线程的消息。当线程没有共享内存，无法共享监视器、信号量或任何其他共享变量来进行通信时，就会使用它。以下是消息传递技术的主要优势:

1.  This model is easier to implement than the shared memory model.
2.  It is much easier to implement this model in order to build parallel hardware because it can tolerate higher communication delay.

在 OOPs 中，有很多方法可以实现消息传递技术，比如通过构造函数传递消息、通过方法传递消息或者通过传递不同的值。下面是通过值传递消息技术的简单实现:

## 【Java】

```
// Java program to demonstrate
// message passing by value

import java.io.*;

// Implementing a message passing
// class
public class MessagePassing {

    // Implementing a method to
    // add two integers
    void displayInt(int x, int y)
    {
        int z = x + y;
        System.out.println(
            "Int Value is : " + z);
    }

    // Implementing a method to multiply
    // two floating point numbers
    void displayFloat(float x, float y)
    {
        float z = x * y;
        System.out.println(
            "Float Value is : " + z);
    }
}
class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a new object
        MessagePassing mp
            = new MessagePassing();

        // Passing the values to compute
        // the answer
        mp.displayInt(1, 100);
        mp.displayFloat((float)3, (float)6.9);
    }
}
```

**输出:**

```
Int Value is : 101
Float Value is : 20.7

```