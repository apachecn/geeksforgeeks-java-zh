# 实现可运行的内部类和匿名内部类|并发编程方法 3

> 原文:[https://www . geesforgeks . org/内部类和匿名内部类实现可运行并发编程方法-3/](https://www.geeksforgeeks.org/inner-class-and-anonymous-inner-class-that-implements-runnable-concurrent-programming-approach-3/)

**先决条件:**[Java 中并发编程的不同方法](https://www.geeksforgeeks.org/different-approaches-to-concurrent-programming-in-java/)

### 实现可运行的内部类

1.  在这种方法中，用户实际上将实现 Runnable 的类的类定义放在主类的类定义中。

    ```java
    public class OuterClass{
        private class InnerClass implements Runnable{
            public void run(){
            }
        }
    }

    ```

2.  run()方法然后被放在内部类中，并被传递给 execute 方法。执行并不真正意味着执行。意思是可供执行。例如，如果用户的池大小为 5，并且任务队列中有 10 个任务，则第 6 个任务直到前 5 个任务中的一个完成后才会开始执行。

    ```java
    taskList.execute(new InnerClass());

    ```

**实际执行:**

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

// Java Program to depict Concurrent
// Programming in action
public class OuterClass {

    // Driver method
    public static void main(String[] args)
    {
        new OuterClass().startThreads();
    }

    // Starts the threads and calls run method
    // method of the runnable interface
    private void startThreads()
    {
        ExecutorService taskList
            = Executors.newFixedThreadPool(2);

        taskList.execute(new InnerClass(1));
        taskList.execute(new InnerClass(2));
        taskList.execute(new InnerClass(3));
        taskList.execute(new InnerClass(4));
        taskList.execute(new InnerClass(5));
        taskList.shutdown();
    }

    // Pauses execution allowing time for
    // system to switch back and forth
    private void pause(double seconds)
    {
        try {
            Thread.sleep(Math.round(1000.0 * seconds));
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }
    }

    // Inner Class
    public class InnerClass implements Runnable {

        private int loopLimit;

        // Constructor to define
        // different limits
        InnerClass(int loopLimit)
        {
            this.loopLimit = loopLimit;
        }

        // Prints thread name and value
        // of the counter variable
        @Override
        public void run()
        {
            for (int i = 0; i < loopLimit; i++) {
                System.out.println(
                    Thread.currentThread().getName()
                    + " Counter: " + i);
                pause(Math.random());
            }
        }
    }
}
```

**输出:**

```java

pool-1-thread-1 Counter: 0
pool-1-thread-2 Counter: 0
pool-1-thread-1 Counter: 0
pool-1-thread-2 Counter: 1
pool-1-thread-1 Counter: 1
pool-1-thread-2 Counter: 0
pool-1-thread-2 Counter: 1
pool-1-thread-1 Counter: 2
pool-1-thread-1 Counter: 0
pool-1-thread-2 Counter: 2
pool-1-thread-1 Counter: 1
pool-1-thread-2 Counter: 3
pool-1-thread-1 Counter: 2
pool-1-thread-1 Counter: 3
pool-1-thread-1 Counter: 4

```

**优势:**

1.  访问主应用程序很容易，因为内部类中的方法可以访问外部类的任何公共或私有方法或实例变量。
2.  与单独的类一样，用户可以将参数传递给构造函数，构造函数将它们存储在运行使用的实例变量中。

**缺点:**

1.  紧密耦合有一个缺点，因为 run 方法与此应用密切相关。run 方法不能在其他地方重用。
2.  比赛条件存在严重的危险。当用户想要访问共享数据(主应用程序中的数据)时，会专门使用内部类。

### 实现可运行的匿名内部类

**匿名内部类:**内部类在应用程序中使用非常频繁，以至于开发人员经常希望通过使用匿名内部类来缩短语法，在匿名内部类中，用户一次性给出类定义并实例化该类。由于匿名内部类是内部类，它们与内部类有相同的优点，但它们更短、更简洁。它们带来的缺点是，它们对初学者来说更容易混淆，没有构造函数，并且不能在其他地方重用。

**实际执行:**

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

// Concurrent programming using
// Anonymous Inner Class
public class MyClass {

    // Driver method
    public static void main(String[] args)
    {
        new MyClass().startThreads();
    }

    // Starting threads with pool size as 2
    private void startThreads()
    {
        ExecutorService taskList
            = Executors.newFixedThreadPool(2);

        for (int i = 0; i < 5; i++) {
            int finalI = i + 1;

            // Giving the class definition
            // and instantiating it all at once
            taskList.execute(new Runnable() {

                // Prints thread name and value
                // of the counter variable
                @Override
                public void run()
                {
                    for (int j = 0; j < finalI; j++) {
                        System.out.println(
                            Thread
                                .currentThread()
                                .getName()
                            + " Counter:" + j);
                        pause(Math.random());
                    }
                }
            });
        }
        taskList.shutdown();
    }

    // Pauses execution allowing time for
    // system to switch back and forth
    private void pause(double seconds)
    {
        try {
            Thread.sleep(
                Math.round(1000.0 * seconds));
        }
        catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
pool-1-thread-1 Counter:0
pool-1-thread-2 Counter:0
pool-1-thread-2 Counter:1
pool-1-thread-1 Counter:0
pool-1-thread-2 Counter:0
pool-1-thread-1 Counter:1
pool-1-thread-2 Counter:1
pool-1-thread-1 Counter:2
pool-1-thread-2 Counter:2
pool-1-thread-2 Counter:3
pool-1-thread-1 Counter:0
pool-1-thread-1 Counter:1
pool-1-thread-1 Counter:2
pool-1-thread-1 Counter:3
pool-1-thread-1 Counter:4

```