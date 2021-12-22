# Java 中的 ForkJoinPool 类，示例

> 原文:[https://www . geeksforgeeks . org/forkjoinpool-in-Java-class-with-examples/](https://www.geeksforgeeks.org/forkjoinpool-class-in-java-with-examples/)

**ForkJoinPool** 类是 fork/join 框架的中心，是 ExecutorService 接口的实现。ForkJoinPool 类是 AbstractExecutorService 类的扩展，它实现了 fork/join 框架的工作窃取算法(即用完要做的事情的工作线程可以从其他仍然忙碌的线程中窃取任务)，并可以执行 ForkJoinTask 进程。

**ForkJoinPool 类继承了 Java . util . concurrent . abstractexecutorservice 类的以下方法:**

*   invokeAll()
*   invokeAny()

**ForkJoinPool 类继承了从 java.lang.Object 类继承的 methods 的以下方法:**

*   克隆()
*   等于()
*   最终确定()
*   getClass()
*   hashCode()
*   通知()
*   notifyAll()
*   等待()

**语法:**

```
public class ForkJoinPool extends AbstractExecutorService  
```

**Fork:** Fork 步骤将任务拆分成更小的子任务，这些任务同时执行。

**连接:**子任务执行后，任务可以将所有结果连接成一个结果。

**如下图所示:**

![ForkJoinPool-Class-in-Java-with-Examples](img/fd460403350493ca866049eb675f5a3e.png)

**示例:**

**getActiveThreadCount():** 此方法返回当前正在窃取或执行任务的估计线程数。它可能高估了活动线程的数量。

**语法**

```
public int getActiveThreadCount()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// Implementation of getActiveThreadCount()

import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.RecursiveAction;
class NewTask extends RecursiveAction
{
    private long Load = 0;

    public NewTask(long Load) { this.Load = Load; }

    protected void compute()
    {
        // fork tasks into smaller subtasks
        List<NewTask> subtasks = new ArrayList<NewTask>();
        subtasks.addAll(createSubtasks());

        for (RecursiveAction subtask : subtasks) {
            subtask.fork();
        }
    }

    // function to create and add subtasks
    private List<NewTask> createSubtasks()
    {
        // create subtasks
        List<NewTask> subtasks = new ArrayList<NewTask>();
        NewTask subtask1 = new NewTask(this.Load / 2);
        NewTask subtask2 = new NewTask(this.Load / 2);
        NewTask subtask3 = new NewTask(this.Load / 2);

        // to add the subtasks
        subtasks.add(subtask1);
        subtasks.add(subtask2);
        subtasks.add(subtask3);

        return subtasks;
    }
}
public class JavaForkJoingetActivethreadcountExample1 {
    public static void main(final String[] arguments)
        throws InterruptedException
    {
        // get no. of available core available
        int proc = Runtime.getRuntime().availableProcessors();

        System.out.println("Number of available core in the processor is: "
            + proc);

        // get no. of threads active
        ForkJoinPool Pool = ForkJoinPool.commonPool();

        System.out.println("Number of active thread before invoking: "
            + Pool.getActiveThreadCount());

        NewTask t = new NewTask(400);

        Pool.invoke(t);

        System.out.println("Number of active thread after invoking: "
            + Pool.getActiveThreadCount());
        System.out.println("Common Pool Size is: "
                           + Pool.getPoolSize());
    }
}
```

**Output**

```
Number of available core in the processor is: 4
Number of active thread before invoking: 0
Number of active thread after invoking: 3
Common Pool Size is: 3
```

### 分叉连接池类的方法

<figure class="table">

| 

**方法**

 | 

**描述**

 |
| --- | --- |
| 公共布尔值唤醒静止(长超时，时间单位单位) | 此方法执行池直到池静止，否则，协助执行任务直到指定的时间值和单位过去或池静止。 |
| 公共布尔预警终端(长超时，时间单位单位) | 此方法会一直阻塞，直到所有任务在关闭请求后完成执行，或者发生超时，或者当前线程被中断，以先发生的为准。 |
| 公共静态 ForkJoinPool commonPool() | 此方法返回公共池实例。 |
| 公共无效执行(可运行任务) | 这个方法在将来的某个时候执行给定的命令。 |
| public int getActiveThreadCount() | 此方法返回当前正在窃取或执行任务的估计线程数。它可能高估了活动线程的数量。 |
| 公共布尔 getAsyncMode() | 如果此池对从未加入的分叉任务使用本地先进先出调度模式，则此方法返回 true。 |
| 公共静态 int getCommonPoolParallelism() | 此方法返回公共池的目标并行度。 |
| 公共 ForkJoinPool。ForkJoinWorkerThreadFactory getFactory() | 此方法返回用于建造新工人的工厂。 |
| public int getParallelism() | 此方法返回该池的目标并行度。 |
| public int getpoolsize() | 此方法返回已经启动但尚未终止的工作线程数。 |
| public int getquedsubmissioncount() | 此方法返回提交给此池但尚未开始执行的任务数的估计值。 |
| 公共长 getQueuedTaskCount() | 此方法返回工作线程当前在队列中持有的任务总数的估计值 |
| public int 增强线程计数() | 此方法返回未被阻止等待加入任务或等待其他托管同步的工作线程数的估计值。 |
| public long getStealCount() | 此方法返回一个线程从另一个线程的工作队列中窃取的任务总数的估计值。 |
| 公共线程。uncaught xception handler getuncautexception handler() | 此方法返回由于执行任务时遇到不可恢复的错误而终止的内部工作线程的处理程序。 |
| 公共布尔 hasQueuedSubmissions() | 如果有任何提交到此池的任务尚未开始执行，此方法将返回 true。 |
| 公共 <t>T 调用(ForkJoinTask <t>任务)</t></t> | 此方法执行给定的任务，并在完成时返回其结果。 |
| 公共布尔值 isstatic() | 如果所有工作线程当前都处于空闲状态，则此方法返回 true。 |
| 公共布尔值 isShutdown() | 如果调用 isShutdown()的池已关闭，则此方法返回 true。 |
| 公共布尔值 isTerminated() | 如果关闭后所有任务都已完成，则此方法返回 true。 |
| 公共布尔寄存器化() | 如果终止过程已经开始但尚未完成，则此方法返回 true。 |
| 受保护的<t>运行未来<t>新任务器(可调用<t>可调用)</t></t></t> | 这个方法返回一个 RunnableFuture，当运行时，它将调用底层的可调用函数，作为一个 Future，它将产生可调用函数的结果作为它的结果，并提供底层任务的取消。 |
| 公共无效关闭() | 如果此池已关闭，此方法返回 true。 |
| 公共列表<runnable>关闭现在()</runnable> | 此方法可能会尝试取消和/或停止所有任务，并拒绝所有后续提交的任务。 |
| 公共分叉联合任务>提交(可运行任务) | 这个方法提交一个可运行的任务来执行，并返回一个代表该任务的未来。 |
| 公共字符串 toString() | 此方法返回一个字符串，该字符串标识该池及其状态，包括运行状态、并行度以及工作进程和任务计数的指示。 |

</figure>