# Java 中 BlockingDeque takeLast()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-take last-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-takelast-method-in-java-with-examples/)

**封锁请求**的 **takeLast()** 方法返回并移除德格集装箱的尾部。如果在等待时被中断，该方法将抛出*中断异常*。

**语法:**

```
public E takeLast()

```

**返回:**该方法返回德雀容器的**尾(最后一个元素)**。

**异常**:如果在等待时被中断，该功能会抛出*中断异常*。

**注**:**blocking request**的 **takeLast()** 方法继承自 Java 中的 LinkedBlockingDeque 类。

下面的程序说明了 *takeLast()* 阻塞请求的方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate takeLast()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        // removes the last element and prints it
        System.out.println("Head of Blocking Deque: "
                           + BD.takeLast());

        // prints the Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**Output:** 

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Blocking Deque: 74381793
Blocking Deque: [7855642, 35658786, 5278367]

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate takeLast()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        BD.clear();

        // throws error as the list is empty and it
        // is interrupted while waiting
        System.out.println("Head of Blocking Deque: "
                           + BD.takeLast());
    }
}
```

**运行时错误:**

```
Max real time limit exceeded due to either by heavy load on server or by using sleep function

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # take last()T4】