# Java . util . concurrent . executor 接口示例

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-executor-interface-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/)

Java 中的并发应用编程接口提供了一个名为**执行器**的特性，即**启动并控制线程**的执行。因此，执行器提供了一种使用线程类管理线程的替代方法。执行器的核心是**执行器**界面。它指的是执行提交的可运行任务的对象。

**等级等级:**

```
java.util.concurrent
  ↳ Interface Executor
```

**实现子接口:**

```
ExecutorService
ScheduledExecutorService
```

**实现类:**

```
AbstractExecutorService
ForkJoinPool
ScheduledThreadPoolExecutor
ThreadPoolExecutor
```

**执行器界面的方法:**

1.  **execute()** :该函数在未来某个时间执行给定的命令。根据执行器实现的判断，该命令可以在新线程、池线程或调用线程中执行。
    **语法:**

```
void execute(Runnable task)
```

**演示执行器的示例。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.concurrent.Executor;
import java.util.concurrent.RejectedExecutionException;

public class ExecutorDemo {
    public static void main(String[] args)
    {
        ExecutorImp obj = new ExecutorImp();
        try {
            obj.execute(new NewThread());
        }
        catch (RejectedExecutionException
               | NullPointerException exception) {
            System.out.println(exception);
        }
    }
}

class ExecutorImp implements Executor {
    @Override
    public void execute(Runnable command)
    {
        new Thread(command).start();
    }
}

class NewThread implements Runnable {
    @Override
    public void run()
    {
        System.out.println("Thread executed under an executor");
    }
}
```

**Output:** 

```
Thread executed under an executor
```

**参考:**T2T4】