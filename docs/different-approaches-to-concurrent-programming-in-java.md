# Java 并发编程的不同方法

> 原文:[https://www . geesforgeks . org/Java 并发编程的不同方法/](https://www.geeksforgeeks.org/different-approaches-to-concurrent-programming-in-java/)

本文展示了如何使用 Java 线程框架执行并发编程。让我们首先分析并发编程:

**并发编程:**这意味着任务似乎是同时运行的，但在幕后，系统可能真的在任务之间来回切换。并发编程的要点是，即使在单处理器机器上，它也是有益的。

**单处理器机器上的并发编程:**

1.  假设用户需要下载五个图像，每个图像来自不同的服务器，每个图像需要五秒钟，现在假设用户下载所有的第一个图像，需要 5 秒钟，然后下载所有的第二个图像，需要 5 秒钟，以此类推，到时间结束时，需要 25 秒钟。先下载一点图片一，然后再下载一点图片二、三、四、五，然后回来再下载一点图片一等等，速度会更快。

    ```

             Tasks overlap in time

    Task1   ------   ------   ------    ------ 

    Task2       ------   ------   ------   ------ 

            ------------------------------------------>
                                 Time

    ```

2.  如果每一个都需要 5 秒钟，并将其分成小块，总和仍然是 25 秒。那么为什么并发下载会更快呢？
3.  这是因为当来自第一个服务器的图像被调用时，它需要 5 秒钟，这不是因为传入的带宽被最大化，而是因为服务器需要一段时间才能将其发送给用户。基本上，用户大部分时间都坐在那里等待。因此，当用户在等待第一个图像时，他也可能开始下载第二个图像。因此，如果服务器运行缓慢，通过在多个线程中同时运行，可以下载额外的图像，而无需太多额外的时间。
4.  现在，最终，如果一个人同时下载大量图像，传入的带宽可能会达到最大值，然后添加更多线程不会加快速度，但在某种程度上，这是免费的。
5.  除了速度，另一个优势是减少延迟。一次做一点点可以减少延迟，这样用户就可以随着事情的进展看到一些反馈。

**并发编程的需要**

*   线程只有在任务相对较大并且非常独立的时候才有用。当用户在大量的单独处理之后只需要执行少量的组合时，启动和使用线程会有一些开销。所以如果任务真的很小，一个人永远得不到开销的回报。
*   同样，如上所述，当用户等待时，线程是最有用的。例如，当一个正在等待一个服务器时，另一个可以从另一个服务器读取。

**并发编程的基本步骤**

1.  首先要排队一个任务。调用执行器服务指向新的固定线程池并提供一个大小。此大小表示同时进行的任务的最大数量。例如，如果一个人向队列中添加了一千个东西，但是池的大小是 50，那么在任何时候都只有 50 个在运行。只有当前五十个中的一个完成执行时，第五十一个才会被执行。像池大小为 100 这样的数字不会使系统过载。

    ```
    ExecutorService taskList = Executors.newFixedThreadPool(poolSize);

    ```

2.  然后，用户必须将一些可运行类型的任务放到任务队列中。Runnable 只是一个接口，它有一个叫做 run 的方法。当系统通过启动单独的线程在任务之间来回切换时，它会在适当的时间调用 run 方法。

    ```
     taskList.execute(someRunnable)
    ```

3.  Execute 方法有点用词不当，因为当一个任务被添加到上面用 executors 创建的队列中的任务点新的固定线程池时，它不一定会立即开始执行。当其中一个同时执行的(池大小)完成执行时，它开始执行。

实现并发编程有五种不同的方法，各有优缺点。我们将在本文中讨论第一种方法，并在后续文章中讨论其余方法。

**方法一:实现可运行的独立类**

1.  首先要做的是创建一个单独的类，一个完全单独的类，实现可运行的接口。

    ```
    public class MyRunnable implements Runnable {
             public void run() { ... }  
    }
    ```

2.  其次，创建主类的一些实例，并将它们传递给执行。让我们将这第一种方法应用到只需要计数的线程中。所以，每个线程都会打印线程名、任务号和计数器值。
3.  接下来，使用暂停方法等待，以便系统来回切换。因此，打印语句将是交错的。
4.  将构造函数参数传递给 Runnable 的构造函数，这样不同的实例将计数不同的次数。
5.  调用 shutdown 方法意味着关闭正在监视的线程，看看是否添加了任何新任务。

**实际执行**

```
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

/**
* @author evivehealth on 08/02/19.
*/
// Java program depicting 
// concurrent programming in action.

// Runnable Class that defines the logic
// of run method of runnable interface
public class Counter implements Runnable 
{
    private final MainApp mainApp;
    private final int loopLimit;
    private final String task;

    // Constructor to get a reference to the main class
    public Counter
          (MainApp mainApp, int loopLimit, String task)
    {
        this.mainApp = mainApp;
        this.loopLimit = loopLimit;
        this.task = task;
    }

    // Prints the thread name, task number and 
    // the value of counter
    // Calls pause method to allow multithreading to occur
    @Override
    public void run()
    {
        for (int i = 0; i < loopLimit; i++) 
        {
            System.out.println("Thread: " +
            Thread.currentThread().getName() + " Counter: "
                             + (i + 1) + " Task: " + task);
            mainApp.pause(Math.random());
        }
    }
}
class MainApp 
{

    // Starts the threads. Pool size 2 means at any time
    // there can only be two simultaneous threads
    public void startThread()
    {
        ExecutorService taskList = 
                         Executors.newFixedThreadPool(2);
        for (int i = 0; i < 5; i++) 
        {
            // Makes tasks available for execution.
            // At the appropriate time, calls run 
            // method of runnable interface
            taskList.execute(new Counter(this, i + 1,
                                    "task " + (i + 1)));
        }

        // Shuts the thread that's watching to see if 
        // you have added new tasks.
        taskList.shutdown();
    }

    // Pauses execution for a moment
    // so that system switches back and forth
    public void pause(double seconds)
    {
        try 
        {
            Thread.sleep(Math.round(1000.0 * seconds));
        }
        catch (InterruptedException e)
        {
            e.printStackTrace();
        }
    }

    // Driver method
    public static void main(String[] args)
    {
        new MainApp().startThread();
    }
}
```

**Output:**

```
Thread: pool-1-thread-1 Counter: 1 Task: task 1
Thread: pool-1-thread-2 Counter: 1 Task: task 2
Thread: pool-1-thread-2 Counter: 2 Task: task 2
Thread: pool-1-thread-1 Counter: 1 Task: task 3
Thread: pool-1-thread-2 Counter: 1 Task: task 4
Thread: pool-1-thread-1 Counter: 2 Task: task 3
Thread: pool-1-thread-1 Counter: 3 Task: task 3
Thread: pool-1-thread-1 Counter: 1 Task: task 5
Thread: pool-1-thread-2 Counter: 2 Task: task 4
Thread: pool-1-thread-2 Counter: 3 Task: task 4
Thread: pool-1-thread-1 Counter: 2 Task: task 5
Thread: pool-1-thread-2 Counter: 4 Task: task 4
Thread: pool-1-thread-1 Counter: 3 Task: task 5
Thread: pool-1-thread-1 Counter: 4 Task: task 5
Thread: pool-1-thread-1 Counter: 5 Task: task 5

```

**优势:**

*   **松耦合:**由于一个单独的类可以被重用，所以它促进了松耦合。
*   **构造函数:**对于不同的情况，可以将参数传递给构造函数。例如，描述线程的不同循环限制。
*   **比赛条件:**如果数据已经共享，不太可能使用单独的类作为方法，如果没有共享的数据，那么就不需要担心比赛条件。

**缺点:**
回呼主应用有点不方便。引用必须沿着构造函数传递，即使可以访问引用，也只能调用主应用程序中的公共方法(在给定示例中是 pause 方法)。