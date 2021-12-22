# Java 执行器框架中的 CustomThreadPoolExecutor

> 原文:[https://www . geeksforgeeks . org/customthreadpoolexecutor-in-Java-executor-framework/](https://www.geeksforgeeks.org/customthreadpoolexecutor-in-java-executor-framework/)

[执行器](https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/)管理线程执行。在执行器的顶部，层次结构是执行器接口，用于启动线程。[执行器服务](https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/)扩展执行器并提供管理执行的方法。ExecutorService 有三种实现:ThreadPoolExecutor、ScheduledThreadPoolExecutor 和 ForkJoinPool。java.util.concurrent 还定义了 executors 实用程序类，其中包括一些静态方法，可以简化各种 Executors 的创建。与执行器相关的是 Future 和 Callable 接口。未来包含线程执行后返回的值。因此，当线程终止时，它的值被定义为“将来”。Callable 定义了一个返回值的线程。在本文中，我们将学习 java 中的自定义线程池执行器。

首先，让我们讨论两个在这里被积极使用的概念，即线程池和阻塞队列。

1.  线程池是一个容器，其中包含一些线程。这些线程被赋予一些任务。当一个线程完成它的任务时，下一个任务就交给它了。在多线程环境中工作时，为每个新任务创建新的单独线程是不切实际的，因为创建新线程会增加操作系统的开销。
2.  阻塞队列是这样一种队列，当您尝试从它出列并且队列为空时，它会阻塞。如果您尝试将项目入队到 t，并且队列已经满了。阻塞队列中的所有操作都是线程安全的。

此外，要实施的重要具体方法如下:

**方法 1:** 执行()

该方法包含在执行器接口中。这个函数在将来的某个时候执行给定的任务。它不返回任何东西，因此这个方法的返回类型是无效的。

**方法 2：** myNewFixedThreadPool（）

这是 Executors 类的工厂方法。它用于在线程池中创建固定数量的线程。

*   **参数:**整数线程数
*   **返回类型:**执行服务**T3】**

**程序:**

1.  创建一个接口，我们将在其中创建一个执行方法。这个方法将执行分配给它的任务。
2.  在上面生成的代码中，我们实现了一个可运行的接口。我们正在以 1000 毫秒的延迟打印线程的当前名称。这些是我们将要执行的任务。
3.  MyExecutor 类提供了一个静态方法 myNewFixedThreadPool，我们将在其中传递想要创建的线程数量。这个方法告诉线程池线程池中有多少线程。这些线程将执行任务，直到所有任务完成。
4.  这是自定义线程池类。这个类是整个机制的核心。它使用了两个重要的概念:链接队列和执行类。执行类将进一步解释。这个类从 myNewFixedThreadPool 方法接收线程计数。我们提交的所有任务都存储在队列中。所有线程都将从队列中获取任务。我们使用 MyExecuorService 的执行方法提交任务。
5.  Execution 类执行非常重要的任务，即在线程池中添加创建我们想要的线程数量。这个类是我们定义如何从 LinkedBlockingQueue 获取任务的地方。
6.  最后，在这个类中，我们将所有的部分收集在一起，我们的定制线程池已经准备好了。

**实现:**这里我们将一些线程作为 3 传递。任务数为 20，使用 execute 方法执行。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Concept of
// CustomThreadPoolExecutor Executor Framework

// Importing LinkedBlockingQueue class from java.util
// package
import java.util.concurrent.LinkedBlockingQueue;

// Interface
// Custom interface for which contains execute method
interface MyExecutorService {

    // Method
    void execute(Runnable r);
}

// Class 1
// Helper class
class MyExecutors {

    // Member variables of this class
    int capacity;

    // Passing the number of threads that
    // will be in the thread pool
    static MyExecutorService
    myNewFixedThreadPool(int capacity)
    {

        return new MyThreadPool(capacity);
    }
}

// Class 2
// Helper class extending to MyExecutorService interface
class MyThreadPool implements MyExecutorService {

    // Member variables of this class
    static int capacity;
    static int currentCapacity;

    // Creating object of LinkedBlockingQueue class
    // Declaring object of type Runnable
    static LinkedBlockingQueue<Runnable>
        linkedTaskBlockingQueue;

    // Member variables of this class
    Execution e;

    // Method 1
    public MyThreadPool(int capacity)
    {

        // Member variables of this class

        // this keyword refers to current instance itself
        this.capacity = capacity;
        currentCapacity = 0;

        // Creating a linked blocking queue which will block
        // if its empty
        // and it will perform thread safe operation.
        linkedTaskBlockingQueue
            = new LinkedBlockingQueue<Runnable>();

        // Creating the object of execution class
        e = new Execution();
    }

    // Method 2
    // @Override
    public void execute(Runnable r)
    {

        // Declaring and adding tasks to
        // blocking queue using add() method
        linkedTaskBlockingQueue.add(r);

        // executeMyMethod() method of Execution class
        // which will execute the tasks
        e.executeMyMethod();
    }
}

// Class 3
// Helper class extending Runnable interface
class Execution implements Runnable {

    // Method 1 of  this class
    void executeMyMethod()
    {

        // At start the current capacity will be 0
        // The another capacity is the number of threads we
        // want to create so we will increase the current
        // capacity count after creating each thread it
        // means that we will create the threads if the
        // current capacity is less than capacity passed by
        // us i.e number of threads we want to create.

        // In this case 3 threads will get created
        if (MyThreadPool.currentCapacity
            < MyThreadPool.capacity) {
            MyThreadPool.currentCapacity++;

            // Creating object of Thread class
            Thread t = new Thread(new Execution());

            // Starting the thread
            t.start();
        }
    }

    // Method 2 of this class
    // @Override
    public void run()
    {

        // Till it is true
        while (true) {

            // Here we are fetching the tasks from the
            // linkedblocking queue
            // which we have submitted using execute method
            // and executing them
            if (MyThreadPool.linkedTaskBlockingQueue.size()
                != 0) {
                MyThreadPool.linkedTaskBlockingQueue.poll()
                    .run();
            }
        }
    }
}

// Class 4
// Helper class
// Here we are creating a simple task
// which is printing current thread name
class Mytask implements Runnable {

    // Method 1 of this class
    // @Override
    public void run()
    {

        // Try block to check for exceptions
        try {

            // Making thread to pause fo a second
            // using sleep() method
            Thread.sleep(1000);
        }

        // Catch block to check for exceptions
        catch (InterruptedException e) {

            // Print the exception scaling ith line number
            // using printStackrace() method
            e.printStackTrace();
        }

        // Print and display the current thread using
        // currentThread() method by getting thread name
        // using getName() method
        System.out.println(
            "Current Thread :-> "
            + Thread.currentThread().getName());
    }
}

// Class 5
// Main Class
public class ExecutorServiceCustom {
    // Main driver method
    public static void main(String[] args)
    {
        // Getting the object of MyExcutorService by using
        //  the factory method myNewFixedThreadPool

        // Passing number of threads as 3
        MyExecutorService service
            = MyExecutors.myNewFixedThreadPool(3);

        for (int i = 0; i < 20; i++) {

            // Creating 20 tasks and passing them to execute
            service.execute(new Mytask());
        }

        Runnable runnableTask = null;
    }
}
```

**输出:**

```java
Current Thread :-> Thread-0
Current Thread :-> Thread-1
Current Thread :-> Thread-2
Current Thread :-> Thread-0
Current Thread :-> Thread-1
Current Thread :-> Thread-2
Current Thread :-> Thread-0
Current Thread :-> Thread-1
Current Thread :-> Thread-2
Current Thread :-> Thread-0
Current Thread :-> Thread-1
Current Thread :-> Thread-2
Current Thread :-> Thread-0
Current Thread :-> Thread-1
Current Thread :-> Thread-2
Current Thread :-> Thread-0
Current Thread :-> Thread-1
Current Thread :-> Thread-2
Current Thread :-> Thread-0
Current Thread :-> Thread-1
```

> **注意:**在上面的输出中，我们已经打印了可运行文件中定义的线程名称 20 次，因为我们已经提交了 20 个任务，这些任务通过下面的视频进行了可视化描述

<video class="wp-video-shortcode" id="video-594116-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210425230954/threadPoolExecutor.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210425230954/threadPoolExecutor.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210425230954/threadPoolExecutor.mp4)</video>