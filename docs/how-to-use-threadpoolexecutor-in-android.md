# 如何在安卓系统中使用 ThreadPoolExecutor？

> 原文:[https://www . geesforgeks . org/how-用法-threadpoolexecutor-in-Android/](https://www.geeksforgeeks.org/how-to-use-threadpoolexecutor-in-android/)

任务队列包含等待池中任何空闲线程执行的作业。生产者向队列贡献任务，而工作线程充当消费者，每当空闲线程准备进行新的后台操作时，就从队列中消费作业。

**但是在我们深入之前，安卓中到底什么是线程池？**

它是一个线程池器，负责处理所有与线程相关的任务，尽管线程的适当数量与线程池器的实现方式成正比。

### 线程池执行器

*线程池执行器*使用线程池中的一个线程来完成特定的作业。

## Java 语言(一种计算机语言，尤用于创建网站)

```
ThreadPoolExecutor gfgPoolExecutor
    = new ThreadPoolExecutor(
        int mainPoolSize,
        long keepAliveTime,
          int maximumPoolSize,
        TimeUnit unit,
        BlockingQueue<Runnable> workQueue
    );
```

你可能想知道所有这些价值观指的是什么，对吗？

*   **mainPoolSize** :始终保持在池中的线程数。一开始池中没有线程。但是，当作业添加到队列中时，会生成新的线程。如果有空闲线程，但线程数小于主池大小，将继续生成新线程。
*   **keepAliveTime:** 当线程数超过核心线程数时，非核心线程(额外空闲线程)将等待新作业，如果在此参数指示的时间段内没有得到新作业，将终止。
*   **maximumPoolSize:** 可以同时在池中的最大线程数。如果这超过了主池大小，并且当前线程数超过了主池大小，则只有当队列为空时，才会生成额外的工作线程。
*   **单位:【keepAliveTime 的时间单位。**
*   **工作队列:**任务队列，只保存可以执行的作业。这将是一个阻塞队列。

问题出现了，

### 为什么你会在安卓或 Java 应用中使用线程池执行器？

它是一个强大的任务执行框架，因为它允许任务队列插入、任务取消和任务优先级排序。它通过管理线程池中预定数量的线程来降低与线程创建相关的开销。

> **极客提示:**不同线程池可用的线程数量可能因您的需求而异。

### 安卓系统如何使用线程池

**步骤#1:创建一个 GfGThreadMechanism**

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class GfGThreadMechanism implements ThreadFactory {
    private final int gfgPriority;
    public PriorityThreadFactory(int threadPriority) {
        gfgPriority = threadPriority;
    }
    @Override
    public Thread newThread(final Runnable gfgRunner) {
        Runnable wrapperRunnable = new Runnable() {
            @Override
            public void run() {
                try {
                    Process.setThreadPriority(gfgPriority);
                } catch (Throwable t) {

                }
                gfgRunner.run();
            }
        };
        return new Thread(wrapperRunnable);
    }
}
```

**步骤 2:** **创建主线程执行器**

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class MasterThreadExecutor implements Executor {
    private final Handler gfgHandler = new Handler(Looper.getMainLooper());
    @Override
    public void execute(Runnable runnable) {
        gfgHandler.post(runnable);
    }
}
```

**步骤#3:创建一个单独的类来执行**

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class gfgExecutor{

    // Number of threads, are being set here.
    public static final int NUMBER_OF_THREADS = Runtime.getRuntime().availableProcessors();

    // Setting and Monitoring BG Tasks
    private final ThreadPoolExecutor gfgTasks;

    // another executor for handling light feather tasks
    private final ThreadPoolExecutor gfgFeatherTasks;

    // the thread pool which manages the heavy tasks
    private final Executor publicExecutor;

    // an instance of DefaultExecutorSupplier
    private static DefaultExecutorSupplier gfgInstance;

    // returns the instance of DefaultExecutorSupplier
    public static DefaultExecutorSupplier getInstance() {
       if (gfgInstance == null) {
         synchronized(DefaultExecutorSupplier.class){                                                                 
             gfgInstance = new DefaultExecutorSupplier();     
        }
        return gfgInstance;
    }

    // Main Magic Goes Here
    private DefaultExecutorSupplier() {
        // setting the thread factory
        ThreadFactory backgroundPriorityThreadFactory = new
                PriorityThreadFactory(Process.THREAD_PRIORITY_BACKGROUND);

        // setting the thread pool executor for gfgTasks;
        gfgTasks = new ThreadPoolExecutor(
                NUMBER_OF_THREADS * 2,
                NUMBER_OF_THREADS * 2,
                60L,
                TimeUnit.SECONDS,
                new LinkedBlockingQueue<Runnable>(),
                backgroundPriorityThreadFactory
        );

        // setting the thread pool executor for gfgFeatherTasks;
        gfgFeatherTasks = new ThreadPoolExecutor(
                NUMBER_OF_THREADS * 2,
                NUMBER_OF_THREADS * 2,
                60L,
                TimeUnit.SECONDS,
                new LinkedBlockingQueue<Runnable>(),
                backgroundPriorityThreadFactory
        );

        // setting the thread pool executor for gfgExecutor;
        gfgExecutor = new MainThreadExecutor();
    }

    // thread pool which returns the BG task
    public ThreadPoolExecutor forBackgroundTasks() {
        return gfgTasks;
    }

    // similar to the return above, but for feather tasks
    public ThreadPoolExecutor forLightWeightBackgroundTasks() {
        return gfgFeatherTasks;
    }

    // similar to the return above, but for heavy tasks
    public Executor forMainThreadTasks() {
        return mMainThreadExecutor;
    }
}
```

**现在在任何活动中使用这个类，你都准备好了！**

### 你如何区分任务的优先级？

假设一个队列中有 10 个作业，线程池只能处理 4 个线程。因为线程池一次只能执行四个活动，所以我们优先考虑新作业。但是假设我们要求我们放入队列中的最后一个作业首先完成。我们需要赋予该作业立即优先级，这样当线程从队列中获得新任务时，它会首先运行它(因为它具有最高优先级)。要对作业进行优先级排序，我们必须首先构建一个线程池执行器。

**创建优先级枚举:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// The different urgency levels
public enum Urgency {

    // Lowest urgency level
    LOW,

    // Medium urgency level
    MEDIUM,

    // Highest urgency level
    HIGH,

    // Highest urgency level,
    // even up from the previous
    IMMEDIATE;

}
```

然后，我们为紧急情况创建一个可运行的:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class UrgencyRunnable implements Runnable {
    private final Priority gfgUrgency;

    public PriorityRunnable(Priority gfgUrgency) {
        this.gfgUrgency = gfgUrgency;
    }

    @Override
    public void run() {
      // your code, or leave blank.
    }

    public Priority gfgUrgency() {
        return gfgUrgency;
    }
}
```

**通过扩展线程池执行器**使线程池执行器优先。

必须创建优先级未来任务，它将实现<comparablepriorityfuturetask>。</comparablepriorityfuturetask>

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class UrgencyExecutor extends ThreadPoolExecutor {
   public PriorityThreadPoolExecutor(int gfgPool, int gfgMax, long gfgTime,
         TimeUnit unit, ThreadFactory threadFactory) {
        super(gfgPool, gfgMax, gfgTime, unit,new PriorityBlockingQueue<Runnable>(), threadFactory);
    }

    @Override
    public gfgTask<?> submit(Runnable gfgBackTask) {
        PriorityFutureTask gfgTask = new PriorityFutureTask((PriorityRunnable) task);
        execute(gfgTask);
        return gfgTask;
    }
    private static final class PriorityFutureTask extends FutureTask<PriorityRunnable>
            implements Comparable<gfgTask> {
        private final PriorityRunnable priorityRunnable;

        public gfgTask(PriorityRunnable priorityRunnable) {
            super(priorityRunnable, null);
            this.priorityRunnable = priorityRunnable;
        }

        @Override
        public int compareTo(gfgTask other) {
            Priority gfg1 = priorityRunnable.getPriority();
            Priority gfg2 = other.priorityRunnable.getPriority();
            return gfg2.ordinal() - gfg1.ordinal();
        }
    }
}
```

首先，在缺省执行器供应商中使用优先级线程池执行器，而不是线程池执行器，如下所示:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class DefaultExecutorSupplier{
private final PriorityThreadPoolExecutor gfgBackTask;
private DefaultExecutorSupplier() {
        gfgBackTask = new PriorityThreadPoolExecutor(
                NUMBER_OF_THREADS * 4,
                NUMBER_OF_THREADS * 3,
                50L,
                TimeUnit.SECONDS,
                backgroundPriorityThreadFactory
        );
    }
}
```

**下面是一个我们如何将一项工作列为低优先级的例子:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Doing at LOW
public void doingAtLowUrgency(){
  DefaultExecutorSupplier.getInstance().forBackgroundTasks()
    .submit(new PriorityRunnable(Priority.LOW) {
    @Override
    public void run() {
    // some back tasks go here
    }
  });
}
```

### 结论

可以用这种方式对任务进行优先级排序。上述实现也适用于任何 JAVA 应用程序。希望这篇文章为你扫清了空气！