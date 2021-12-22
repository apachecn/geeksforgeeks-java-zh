# 在 Java 中连接线程

> 原文:[https://www.geeksforgeeks.org/joining-threads-in-java/](https://www.geeksforgeeks.org/joining-threads-in-java/)

**java.lang.Thread** 类提供了 join()方法，该方法允许一个线程等待另一个线程完成其执行。如果 **t** 是线程当前正在执行的线程对象，那么 **t.join()** 将确保 **t** 在程序执行下一条指令之前终止。
如果有多个线程调用 join()方法，这意味着 join 上的重载允许程序员指定等待时间。但是，与睡眠一样，连接依赖于操作系统的计时，因此您不应该假设连接会等待您指定的时间。
有三个重载连接函数。

1.  **join():** 它会将当前线程置于 on 状态，直到调用它的线程死亡。如果线程被中断，那么它将抛出中断异常。
    **语法:**

    ```
    public final void join()

    ```

2.  **join(long millis)** :它会将当前线程置于等待状态，直到调用它的线程停止或等待指定的时间(毫秒)。
    **语法:**

    ```
    public final synchronized void join(long millis)

    ```

3.  **join(long millis，int nano):**它会将当前线程置于等待状态，直到调用它的线程停止运行或等待指定的时间(毫秒+nano)。
    **语法:**

```
public final synchronized void join(long millis, int nanos)

```

```
// Java program to explain the
// concept of joining a thread.
import java.io.*;

// Creating thread by creating the
// objects of that class
class ThreadJoining extends Thread
{
    @Override
    public void run()
    {
        for (int i = 0; i < 2; i++)
        {
            try
            {
                Thread.sleep(500);
                System.out.println("Current Thread: "
                        + Thread.currentThread().getName());
            }

            catch(Exception ex)
            {
                System.out.println("Exception has" +
                                " been caught" + ex);
            }
            System.out.println(i);
        }
    }
}

class GFG
{
    public static void main (String[] args)
    {

        // creating two threads
        ThreadJoining t1 = new ThreadJoining();
        ThreadJoining t2 = new ThreadJoining();
        ThreadJoining t3 = new ThreadJoining();

        // thread t1 starts
        t1.start();

        // starts second thread after when
        // first thread t1 has died.
        try
        {
            System.out.println("Current Thread: "
                  + Thread.currentThread().getName());
            t1.join();
        }

        catch(Exception ex)
        {
            System.out.println("Exception has " +
                                "been caught" + ex);
        }

        // t2 starts
        t2.start();

        // starts t3 after when thread t2 has died.
        try
        {
            System.out.println("Current Thread: "
                 + Thread.currentThread().getName());
            t2.join();
        }

        catch(Exception ex)
        {
            System.out.println("Exception has been" +
                                    " caught" + ex);
        }

        t3.start();
    }
}
```

输出:

```
Current Thread: main
Current Thread: Thread-0
0
Current Thread: Thread-0
1
Current Thread: main
Current Thread: Thread-1
0
Current Thread: Thread-1
1
Current Thread: Thread-2
0
Current Thread: Thread-2
1

```

在上面的例子中，我们可以清楚地看到第二个线程 t2 在第一个线程 t1 已经死亡之后开始，而 t3 将在第二个线程 t2 已经死亡之后开始执行。

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。