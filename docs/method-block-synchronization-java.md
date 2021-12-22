# Java 中的方法和块同步

> 原文:[https://www . geesforgeks . org/method-block-synchronization-Java/](https://www.geeksforgeeks.org/method-block-synchronization-java/)

线程主要通过共享对字段和引用字段的对象的访问来进行通信。这种形式的通信效率极高，但却使两种错误成为可能:线程干扰和内存一致性错误。需要一些同步结构来防止这些错误。以下示例显示了我们需要同步的情况。

**需要同步**

考虑以下示例:

```
// Java program to illustrate need
// of Synchronization
import java.io.*;

class Multithread
{
    private int i = 0;
    public void increment()
    {
        i++;
    }

    public int getValue()
    {
        return i;
    }
}

class GfG
{
    public static void main (String[] args)
    {
        Multithread t = new Multithread();
        t.increment();
        System.out.println(t.getValue());
    }
}
```

输出:

```
1
```

在上面的例子中，执行了三个操作:

1.  获取变量 I 的值。
2.  增加提取的值。
3.  把增值的 I 储存到它的位置。

在这里，

*   第一个线程获取 I 的值(当前值 I 为 0)，并将其增加 1，因此变量 I 的值变为 1。
*   现在第二个线程访问 I 的值，该值将为 0，因为第一个线程没有将其存储回其位置。
    第二个线程也将其递增并存储回其位置。1st 也存储它。
*   最后，变量 I 的值是 1。但是受两个线程的影响应该是 2。这就是为什么我们需要同步对共享变量 I 的访问。

Java 是多线程语言，其中多个线程并行运行以完成它们的执行。我们需要同步共享资源，以确保一次只有一个线程能够访问共享资源。
如果一个对象被多个线程共享，那么需要同步，以避免对象的状态被破坏。当对象可变时，需要同步。如果共享对象是不可变的，或者共享同一个对象的所有线程只读取对象的状态而不修改，那么您就不需要同步它。

Java 编程语言提供了两种同步习惯用法:

*   方法同步
*   语句同步(块同步)

**方法同步**

同步方法实现了防止线程干扰和内存一致性错误的简单策略。如果一个对象对多个线程可见，对该对象字段的所有读或写都是通过**同步**方法完成的。

同步方法的两次调用不可能交错。如果一个线程正在执行同步方法，所有其他在同一个对象上调用同步方法的线程将必须等待，直到第一个线程处理完该对象。

**示例:这显示了是否有多个线程在没有同步的情况下访问 getLine()方法。**

```
// Example illustrates multiple threads are executing
// on the same Object at same time without synchronization.
import java.io.*;

class Line
{
    // if multiple threads(trains) will try to
    // access this unsynchronized method,
    // they all will get it. So there is chance
    // that Object's  state will be corrupted.
    public void getLine()
    {
        for (int i = 0; i < 3; i++)
        {
            System.out.println(i);
            try
            {
                Thread.sleep(400);
            }
            catch (Exception e)
            {
                System.out.println(e);
            }
        }
    }
}

class Train extends Thread
{
    // reference to Line's Object.
    Line line;

    Train(Line line)
    {
        this.line = line;
    }

    @Override
    public void run()
    {
        line.getLine();
    }
}

class GFG
{
    public static void main(String[] args)
    {
        // Object of Line class that is shared
        // among the threads.
        Line obj = new Line();

        // creating the threads that are
        // sharing the same Object.
        Train train1 = new Train(obj);
        Train train2 = new Train(obj);

        // threads start their execution.
        train1.start();
        train2.start();
    }
}
```

输出

```
0
0
1
1
2
2

```

可能有两列(两列以上)需要同时使用，因此有碰撞的可能。因此，为了避免冲突，我们需要同步多个想要运行的线路。

**示例:同步访问同一对象上的 getLine()方法**

```
// Example that shows multiple threads
// can execute the same method but in
// synchronized way.
class Line
{

    // if multiple threads(trains) trying to access
    // this synchronized method on the same Object
    // but only one thread will be able
    // to execute it at a time.
    synchronized public void getLine()
    {
        for (int i = 0; i < 3; i++)
        {
            System.out.println(i);
            try
            {
                Thread.sleep(400);
            }
            catch (Exception e)
            {
                System.out.println(e);
            }
        }
    }
}

class Train extends Thread
{
    // Reference variable of type Line.
    Line line;

    Train(Line line)
    {
        this.line = line;
    }

    @Override
    public void run()
    {
        line.getLine();
    }
}

class GFG
{
    public static void main(String[] args)
    {
        Line obj = new Line();

        // we are creating two threads which share
        // same Object.
        Train train1 = new Train(obj);
        Train train2 = new Train(obj);

        // both threads start executing .
        train1.start();
        train2.start();
    }
}
```

输出:

```
0
1
2
0
1
2

```

**块同步**

如果我们只需要执行一些后续代码行，而不是一个方法中的所有代码行(指令)，那么我们应该只同步其中存在所需指令的代码块。
例如，假设有一个方法包含 100 行代码，但是只有 10 行(一个接一个)代码包含代码的关键部分，即这些行可以修改(改变)对象的状态。因此，我们只需要同步这 10 行代码方法，以避免对象状态的任何修改，并确保其他线程可以在同一方法中执行其余行，而不会中断。

```
import java.io.*;
import java.util.*;

public class Geek
{
    String name = "";
    public int count = 0;

    public void geekName(String geek, List<String> list)
    {
        // Only one thread is permitted
        // to change geek's name at a time.
        synchronized(this)
        {
            name = geek;
            count++;  // how many threads change geek's name.
        }

        // All other threads are permitted
        // to add geek name into list.
        list.add(geek);
    }
}

class GFG
{
    public static void main (String[] args)
    {
        Geek gk = new Geek();
        List<String> list = new ArrayList<String>();
        gk.geekName("mohit", list);
        System.out.println(gk.name);

    }
}
```

输出:

```
mohit

```

**重要点:**

*   当线程进入同步方法或块时，它会获取锁，一旦完成任务并退出同步方法，它就会释放锁。
*   当线程进入同步实例方法或块时，它获取对象级锁，当它进入同步静态方法或块时，它获取类级锁。
*   如果同步块中使用的对象为空，Java 同步将引发空指针异常。例如，如果在**同步(实例)**，**实例**为空，那么它将抛出空指针异常。
*   在 Java 中， **wait()，notifyAll()和 notifyAll()** 是同步中使用的重要方法。
*   您不能将 java **同步的**关键字应用于变量。
*   不要在同步块的非最终字段上同步，因为对非最终字段的引用随时可能改变，然后不同的线程可能在不同的对象上同步，即根本没有同步。

**优势**

*   **多线程:**由于 java 是多线程语言，同步是实现共享资源互斥的好方法。
*   **实例和静态方法:**同步的实例方法和同步的静态方法都可以并发执行，因为它们用于锁定不同的对象。

**限制**

*   **并发限制:** Java 同步不允许并发读取。
*   **降低效率:** Java synchronized 方法运行非常慢，可能会降低性能，因此您应该在绝对必要时同步该方法，否则不要同步，并且只同步代码的关键部分。

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。