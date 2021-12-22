# 主应用实现可运行|并发编程方法 2

> 原文:[https://www . geesforgeks . org/main-app-implements-runnable-concurrent-programming-approach-2/](https://www.geeksforgeeks.org/main-app-implements-runnable-concurrent-programming-approach-2/)

**先决条件:**[Java 中并发编程的不同方法](https://www.geeksforgeeks.org/different-approaches-to-concurrent-programming-in-java/)

让我们详细看看第二种方法。

1.  用户拥有实现**可运行**的主类，这是对编译器的承诺，即该类将拥有**运行**方法。

    ```java
    public class MyClass implements Runnable{
        public void run(){

        }
    }

    ```

2.  The user then passes a reference to the main application to the execute method using the **this** keyword.

    ```java
    taskList.execute(this)

    ```

    这是向编译器传达的一种方式，当它开始运行一个特定的任务时，调用它各自的 run 方法。

3.  与[方法一](https://www.geeksforgeeks.org/different-approaches-to-concurrent-programming-in-java/)相比，这种方法的**优势**在于运行方法可以调用主应用程序中的方法，包括私有应用程序中的方法。
4.  这种方法相对于第一种方法的劣势是**比赛条件。**我们之所以把 run 方法放在主应用中，是为了让它可以在主应用中处理数据。如果用户启动多个线程，并且同时修改相同的共享数据，那么就需要担心竞争条件。其次，**没有构造函数**，这使得传递构造函数参数非常困难，因此每个类都是以同样的方式开始的。
5.  **示例代码:**用户在主类中实现了 runnable，同一个类还有一堆其他的方法，用于制作任务队列和调用 execute 方法。

下面是方法一中解释的反例的方法二实现:

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

// Concurrent Programming in action
public class MainAppRunnable implements Runnable {

    private final int loopLimit;

    // Limit till which the counter will run
    private MainAppRunnable(int loopLimit)
    {
        this.loopLimit = loopLimit;
    }

    private void startThreads()
    {

        // Made the task queue
        ExecutorService taskList
            = Executors.newFixedThreadPool(2);

        // Added these to the task queue
        // and made available for execution
        taskList.execute(this);
        taskList.execute(this);
        taskList.execute(this);
        taskList.execute(this);
        taskList.execute(this);

        // Stopped new tasks from being
        // added to the task queue
        taskList.shutdown();
    }

    @Override
    public void run()
    {
        for (int i = 0; i < loopLimit; i++) {
            System.out.println(
                Thread.currentThread().getName()
                + " Counter: " + i);
        }

        // Called private method that is
        // part of the same application
        pause(Math.random());
    }

    // Methods that run uses can be private
    // in this approach
    private void pause(double seconds)
    {
        try {
            Thread
                .sleep(Math.round(seconds * 1000.0));
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }
    }

    // Driver method
    public static void main(String[] args)
    {
        new MainAppRunnable(3).startThreads();
    }
}
```

**输出:**

```java
pool-1-thread-1 Counter: 0
pool-1-thread-2 Counter: 0
pool-1-thread-1 Counter: 1
pool-1-thread-1 Counter: 2
pool-1-thread-2 Counter: 1
pool-1-thread-2 Counter: 2
pool-1-thread-2 Counter: 0
pool-1-thread-2 Counter: 1
pool-1-thread-2 Counter: 2
pool-1-thread-2 Counter: 0
pool-1-thread-2 Counter: 1
pool-1-thread-2 Counter: 2
pool-1-thread-1 Counter: 0
pool-1-thread-1 Counter: 1
pool-1-thread-1 Counter: 2

```