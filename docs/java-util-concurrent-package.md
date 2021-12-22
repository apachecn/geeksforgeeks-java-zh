# java.util .并发包

> 原文:[https://www.geeksforgeeks.org/java-util-concurrent-package/](https://www.geeksforgeeks.org/java-util-concurrent-package/)

**Java 并发**包涵盖了 Java 平台上的**并发、多线程**和**并行**。并发性是并行运行几个或多个程序或应用程序的能力。Java 并发的**骨干**是[线程](https://www.geeksforgeeks.org/java-lang-thread-class-java/#:~:text=Thread%20a%20line%20of%20execution,manage%20the%20behaviour%20of%20threads.) (一个轻量级的进程，有自己的文件和栈，可以访问同一个进程中其他线程的共享数据)。通过异步或并行执行耗时的任务，可以提高程序的吞吐量和交互性

**Java 5** 在 Java 平台⇾ java.util.concurrent package 中增加了一个新的包。这个包有一组类和接口，有助于用 java 开发并发应用程序([多线程](https://www.geeksforgeeks.org/multithreading-in-java/))。在这个包之前，人们需要自己创建他们需要的实用程序类。

### 该包的主要组件/实用程序:

我们将讨论这个包中一些最有用的实用程序。

**1. 执行者**

[执行器](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/&sa=U&ved=2ahUKEwiy4Ku5itzsAhX5yzgGHQaTCGsQFjAAegQIBhAC&usg=AOvVaw2IV998xx2yTHoP3jxZefJG)是一组接口，表示其实现执行任务的对象。任务应该在新线程上运行还是在当前线程上运行取决于实现。因此，我们可以使用这个接口从实际的任务执行机制中分离任务执行流。**执行器不要求任务执行异步。**最简单的就是可执行界面。

```java
public interface Executor {
    void execute( Runnable command );
}
```

要创建一个**执行器实例**，我们需要创建一个调用者。

```java
public class Invoker implements Executor {
   @Override
   public void execute(Runnable r) {
       r.run();
   }
}
```

现在，对于任务的**执行，我们可以使用这个调用者。**

```java
public void execute() {
   Executor exe = new Invoker();
   exe.execute( () -> {
       // task to be performed
   });
}
```

如果执行者不能接受要执行的任务，将抛出**rejected executionexception**。

**2. 执行器服务**

[ExecutorService](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/&sa=U&ved=2ahUKEwi59qPJi9zsAhXU63MBHUViAs0QFjAAegQIABAC&usg=AOvVaw0IhEBEHz6IF5BcFi5N5lk1) 是一个接口，只强制底层实现实现 **execute()** 方法。它扩展了[执行器](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/&sa=U&ved=2ahUKEwiy4Ku5itzsAhX5yzgGHQaTCGsQFjAAegQIBhAC&usg=AOvVaw2IV998xx2yTHoP3jxZefJG)接口，并增加了一系列执行返回值线程的方法。关闭线程池的方法以及实现任务执行结果的能力。

我们需要创建[可运行](https://www.geeksforgeeks.org/runnable-interface-in-java/#:~:text=Runnable%20is%20an%20interface%20that,run()%20method%20of%20Runnable%20.)T3 目标来使用执行器服务。

```java
public class Task implements Runnable {
   @Override
   public void run() {

       // task details
   }
}
```

现在，我们可以创建这个类的对象/实例，并分配任务。我们需要在创建实例时指定[线程池](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/thread-pools-java/&sa=U&ved=2ahUKEwiNwP6ujdzsAhW6I7cAHR7gDEEQFjAAegQIARAC&usg=AOvVaw2cZXMrjPhInZ8goo7M6j0m)的大小。

```java
// 20 is the thread pool size
ExecutorService exec = Executors.newFixedThreadPool(20);
```

对于单线程[执行器服务](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/&sa=U&ved=2ahUKEwi59qPJi9zsAhXU63MBHUViAs0QFjAAegQIABAC&usg=AOvVaw0IhEBEHz6IF5BcFi5N5lk1)实例的创建，我们可以使用**新线程执行器(线程工厂线程工厂)**来创建实例。创建执行器后，我们可以提交任务。

```java
public void execute() {
   executor.submit(new Task());
}
```

另外，我们可以为**提交任务创建一个 Runnable 实例。**

```java
executor.submit(() -> {
   new Task();
});
```

两种现成的终止方法是:

*   **[Shutdown ():** It will wait until all submitted tasks are completed.
*   **Shutdown ow ():** It will immediately terminate all the tasks being executed/to be executed.

还有一种方法是 **awaitTermination()** ，它会强制阻塞，直到所有任务在关闭事件触发的或执行超时发生后完成执行，或者执行线程本身被中断。

```java
try {
   exec.awaitTermination( 50l, TimeUnit.NANOSECONDS );
} catch (InterruptedException e) {
   e.printStackTrace();
}
```

**3。调度执行服务**

它类似于 ExecutorService。不同的是，这个接口可以定期执行任务。[可运行](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/runnable-interface-in-java/&sa=U&ved=2ahUKEwjsn-ncjdzsAhXg6XMBHQKFAroQFjAAegQIBRAC&usg=AOvVaw3O8BLxMjzB4Rc-WStOAocI) 和[可调用](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/callable-future-java/&sa=U&ved=2ahUKEwirx4fljdzsAhWy73MBHXJVAUgQFjAAegQIAhAC&usg=AOvVaw1ytLwOkUACw22AafBoUipF)功能都用于定义任务。

```java
public void execute() {
   ScheduledExecutorService execServ
     = Executors.newSingleThreadScheduledExecutor();

   Future<String> future = executorService.schedule(() -> {
       // ..
       return "Hello world";
   }, 1, TimeUnit.SECONDS);

   ScheduledFuture<?> scheduledFuture = execServ.schedule(() -> {
       // ..
   }, 1, TimeUnit.SECONDS);

   executorService.shutdown();
}
```

[调度执行服务](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/scheduledexecutorservice-interface-in-java/&sa=U&ved=2ahUKEwjQ0sH6jdzsAhUM4XMBHQVMDfQQFjAAegQIBRAC&usg=AOvVaw3ra570659E7WMLHw7aP6b9) 也可以在一些固定延迟后定义一个任务。

```java
executorService.scheduleAtFixedRate(() -> {
   // ..
}, 1, 20, TimeUnit.SECONDS);

executorService.scheduleWithFixedDelay(() -> {
   // ..
}, 1, 20, TimeUnit.SECONDS);
```

这里，

*   **Schedule ATF ixed rate (runnable command, long initialDelay, long period, time unit unit):** This method creates and executes a periodic action, which is first called after the initial delay, and then called within a given time period until the service instance is closed.
*   **Schedule without fixed delay (runnable command, long initialDelay, long delay, time unit unit):** This method creates and executes a periodic action, which is called first after the initial delay provided, and is repeatedly called with a given delay between the end of execution and the next call.

**4。未来**

它代表**异步操作的结果。**其中的方法检查异步操作是否完成，得到完成的结果等。**取消(布尔 isInterruptRunning)** 应用编程接口取消操作并释放执行线程。当值为真时，执行任务的线程将立即终止。否则，所有正在进行的任务都会完成。

代码片段创建了未来的**实例。**

```java
public void invoke() {
   ExecutorService executorService = Executors.newFixedThreadPool(20);

   Future<String> future = executorService.submit(() -> {
       // ...
       Thread.sleep(10000l);
       return "Hello";
   });
}
```

用于检查未来的**结果是否准备好并在计算完成时获取数据的代码。**

```java
if (future.isDone() && !future.isCancelled()) {
   try {
       str = future.get();
   } catch (InterruptedException | ExecutionException e) {
       e.printStackTrace();
   }
}
```

**给定操作的超时规格**。如果花费的时间超过该时间，则抛出**超时异常**。

```java
try {
   future.get(20, TimeUnit.SECONDS);
} catch (InterruptedException | ExecutionException | TimeoutException e) {
   e.printStackTrace();
} 
```

**5 . count down 闩锁**

它是一个实用程序类，阻塞一组**线程**，直到一些操作完成。一个[计数下拉列表](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/countdownlatch-in-java/&sa=U&ved=2ahUKEwj0ioTnmNzsAhUlg-YKHWDaB70QFjAAegQIABAC&usg=AOvVaw0ds2tzavGwmqpilb7GM-CY)由一个计数器(整数类型)初始化。该计数器随着相关线程的执行完成而递减。但是一旦计数器递减到零，其他线程就会被释放。

**6。循环屏障**

[CyclicBarrier](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-concurrent-cyclicbarrier-java/&sa=U&ved=2ahUKEwjl06j4mNzsAhVH6nMBHe4BA1gQFjAAegQIBBAC&usg=AOvVaw26zZ4rZ-tylsOxdxiHwSya) 除了我们可以重用之外，几乎和 CountDownLatch 一样。它允许多个线程在调用最终任务之前使用 **await()** 相互等待，这个特性不在 CountDownLatch 中。

我们需要创建一个可运行任务的实例来启动屏障条件。

```java
public class Task implements Runnable {

   private CyclicBarrier barrier;

   public Task(CyclicBarrier barrier) {
       this.barrier = barrier;
   }

   @Override
   public void run() {
       try {
           LOG.info(Thread.currentThread().getName() +
             " is waiting");
           barrier.await();
           LOG.info(Thread.currentThread().getName() +
             " is released");
       } catch (InterruptedException | BrokenBarrierException e) {
           e.printStackTrace();
       }
   }

}
```

现在，调用几个线程来竞争屏障条件:

```java
public void start() {

   CyclicBarrier cyclicBarrier = new CyclicBarrier(3, () -> {
       // ..
       LOG.info("All previous tasks completed");
   });

   Thread t11 = new Thread(new Task(cyclicBarrier), "T11");
   Thread t12 = new Thread(new Task(cyclicBarrier), "T12");
   Thread t13 = new Thread(new Task(cyclicBarrier), "T13");

   if (!cyclicBarrier.isBroken()) {
       t11.start();
       t12.start();
       t13.start();
   }
}
```

在上面的代码中， **isBroken()** 方法检查在执行期间是否有任何线程被中断。

**7。信号量**

它用于**阻止**线程级访问逻辑或物理资源的某个部分。[信号量](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/semaphore-in-java/&sa=U&ved=2ahUKEwjMh8nJmdzsAhXXH7cAHQ6CBPUQFjACegQICBAC&usg=AOvVaw0f4I6184vxtsy9oaE5hdEV)包含一组许可。无论线程试图进入关键部分的代码部分，信号量都会给出许可，不管许可是否可用，这意味着关键部分是否可用。如果许可证不可用，则线程不能进入临界区。

它基本上是一个名为 counter 的变量，用于维护从临界区进入和离开线程的计数。当执行线程释放临界区时，计数器增加。

下面的代码用于信号量的实现:

```java
static Semaphore semaphore = new Semaphore(20);

public void execute() throws InterruptedException {

   LOG.info("Available : " + semaphore.availablePermits());
   LOG.info("No. of threads waiting to acquire: " +
     semaphore.getQueueLength());

   if (semaphore.tryAcquire()) {
       try {
           // 
       }
       finally {
           semaphore.release();
       }
   }

}
```

信号量可以用来实现类似**互斥**的数据结构。

**8。螺纹工厂**

它充当线程池**按需创建新线程**。[螺纹工厂](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/threadfactory-interface-in-java-with-examples/&sa=U&ved=2ahUKEwjn7rvhmdzsAhXs73MBHaYZCH4QFjAAegQIABAC&usg=AOvVaw21UyLblvWNnmWtAfiTEs6l)可以定义为:

```java
public class GFGThreadFactory implements ThreadFactory {
   private int threadId;
   private String name;

   public GFGThreadFactory(String name) {
       threadId = 1;
       this.name = name;
   }

   @Override
   public Thread newThread(Runnable r) {
       Thread t = new Thread(r, name + "-Thread_" + threadId);
       LOG.info("created new thread with id : " + threadId +
           " and name : " + t.getName());
       threadId++;
       return t;
   }
}
```

**9。封锁队列**

[【封锁队列】](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/) 接口支持流量控制(除队列外)，如果封锁队列已满或为空，则引入封锁。试图将一个元素排入完整队列的线程被阻塞，直到其他线程通过将一个或多个元素排出队列或完全清除队列而在队列中腾出空间。类似地，它会阻止试图从空队列中删除的线程，直到其他线程插入一个项目。阻塞队列不接受空值。如果我们试图将空项入队，那么它会抛出 **空指针异常** 。

**10。delayqueue〔t1〕**

[延迟队列](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/)是一个专门的[优先级队列](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/)，它根据元素的延迟时间对元素进行排序。这意味着只有那些元素可以从已经过期的队列中取出。DelayQueue 头包含在最短时间内过期的元素。如果没有延迟过期，则没有 head，轮询将返回 null。延迟队列只接受属于延迟类型类的元素。DelayQueue 实现 getDelay()方法返回剩余的延迟时间。

**11 时。锁定**

它是**阻止其他线程**访问某段代码的实用程序。Lock 和 Synchronized 块的区别在于，我们在单独的方法中有 Lock API**Lock()和 unlock()** 操作，而 Synchronized 块完全包含在方法中。

**12 时。相位器**

它比 CountDownLatch 和 CyclicBarrier 更灵活。 [Phaser](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-concurrent-phaser-class-in-java-with-examples/&sa=U&ved=2ahUKEwiKqOSMmtzsAhV97XMBHYz5A_YQFjAAegQIBBAC&usg=AOvVaw3UaufAR-Auid0-ZpNK0LFP) 用作**可重用屏障**，在执行继续之前，动态数量的线程需要在其上等待。通过为每个程序阶段重用 Phaser 实例，可以协调多个执行阶段。