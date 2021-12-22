# λ表达式|并发编程方法 4

> 原文:[https://www . geesforgeks . org/lambda-expressions-concurrent-programming-approach-4/](https://www.geeksforgeeks.org/lambda-expressions-concurrent-programming-approach-4/)

**先决条件:**[Java 中并发编程的不同方法](https://www.geeksforgeeks.org/different-approaches-to-concurrent-programming-in-java/)

Lambda 表达式在行为上与匿名内部类非常相似。他们可以完全访问周围类的代码，包括私有数据。**它们简洁得多，简洁易读**。但是，lambda 表达式不能有实例变量，因此它们不维护状态。

我们可以用 Lambda 表达式替换匿名内部类，如下所示:

**匿名内部类:**

```java
    Thread thread = new Thread(new Runnable() {
      @Override
      public void run() {
        System.out.println("Printed inside Anonymous Inner Class!");
      }
    });

```

**Lambda 表达式:**

> Thread other Thread = new Thread(()->system . out . println(“打印在 Lambda 内部！”));

**实际执行:**

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

// Code for Concurrent programming using
// Lambda Expression
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

            // Prints thread name and value
            // of the counter variable
            taskList.execute(() -> {

                for (int j = 0; j < finalI; j++) {

                    System.out.println(
                        Thread
                            .currentThread()
                            .getName()
                        + " Counter:" + j);
                    pause(Math.random());
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
pool-1-thread-2 Counter:0
pool-1-thread-1 Counter:0
pool-1-thread-2 Counter:1
pool-1-thread-1 Counter:1
pool-1-thread-2 Counter:2
pool-1-thread-1 Counter:2
pool-1-thread-2 Counter:0
pool-1-thread-1 Counter:3
pool-1-thread-2 Counter:1
pool-1-thread-2 Counter:2
pool-1-thread-2 Counter:3
pool-1-thread-2 Counter:4

```

**优势:**用户可以轻松访问主类中的数据，包括私有数据。Lambdas 简洁明了，可读性强。

**缺点:** Lambdas 不允许有实例变量，因此我们不能传递参数来运行方法。此外，当我们有一些共享数据时，我们通常会使用 lambdas，这会带来比赛条件的危险。