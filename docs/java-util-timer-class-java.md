# Java 中的 Java.util.Timer 类

> 原文:[https://www.geeksforgeeks.org/java-util-timer-class-java/](https://www.geeksforgeeks.org/java-util-timer-class-java/)

Timer 类提供了一个方法调用，线程使用该方法调用来调度任务，例如在某个规则的瞬间后运行一个代码块。每个任务可以被安排运行一次或重复执行多次。每个计时器对象都与一个负责执行计时器对象所有任务的后台线程相关联。
**注:**

*   定时器类是线程安全的。
*   计时器类使用二进制堆数据结构来存储其任务。

**施工人员:**

*   **计时器()**:创建新计时器
*   **定时器(布尔型 isDaemon)** :创建一个新的定时器，其关联的线程可以被指定为作为守护进程运行
*   **定时器(字符串名称)**:创建一个新的定时器，其关联的线程具有指定的名称
*   **定时器(字符串名称，布尔型 isDaemon)** :创建一个新的定时器，其关联的线程具有指定的名称，并且可以被指定为作为守护进程运行

**申报:**

```java
public class Timer
 extends Object
```

**从 java.lang.Object 类继承的方法**

*   克隆
*   等于
*   完成
*   getClass(获取类)
*   hashCode(哈希代码)
*   通知
*   notifyAll(通知所有人)
*   toString
*   等待

**方法:**

*   **cancel():Java . util . timer . cancel()**终止此计时器，丢弃任何当前计划的任务。不干扰当前正在执行的任务(如果存在)。一旦定时器被终止，它的执行线程就优雅地终止，并且不能在其上调度更多的任务
    **语法:**

```java
public void cancel()
```

*   **purge():Java . util . timer . purge()**从此计时器的任务队列中移除所有已取消的任务
    **语法:**

```java
public int purge()
Returns:
the number of tasks removed from the queue
```

*   **调度(TimerTask 任务，日期时间):Java . util . timer . schedule(time rtask 任务，日期时间)**调度指定任务在指定时间执行
    T3】语法:

```java
public void schedule(TimerTask task, Date time)
Parameters:
task - task to be scheduled.
time - time at which task is to be executed.
Throws:
IllegalArgumentException - if time.getTime() is negative.
IllegalStateException - if the task was already scheduled or cancelled, 
the timer was cancelled, or timer thread terminated.
NullPointerException - if task or time is null
```

*   **调度(TimerTask 任务，Date firstTime，long period):Java . util . timer . schedule(time rtask 任务，Date firstTime，long period)** 调度指定任务重复固定延迟执行，从指定时间开始
    T3】语法:

```java
public void schedule(TimerTask task, Date firstTime, long period)
Parameters:
task - task to be scheduled.
firstTime - First time at which task is to be executed.
period - time in milliseconds between successive task executions.
Throws:
IllegalArgumentException - if firstTime.getTime() < 0,
 or period <= 0
IllegalStateException - if task was already scheduled 
or cancelled, timer was cancelled, 
or timer thread terminated.
NullPointerException - if task or firstTime is null
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
//schedule method calls of Timer class

import java.util.Timer;
import java.util.TimerTask;

class Helper extends TimerTask
{
    public static int i = 0;
    public void run()
    {
        System.out.println("Timer ran " + ++i);
    }
}

public class Test
{
    public static void main(String[] args)
    {

        Timer timer = new Timer();
        TimerTask task = new Helper();

        timer.schedule(task, 2000, 5000);

    }
}
```

输出:

```java
Timer ran 1
Timer ran 2
Timer ran 3
Timer ran 4
Timer ran 5
.
.
.
```

*   **调度(TimerTask 任务，长延迟):Java . util . timer . schedule(TimerTask 任务，长延迟)**调度指定任务在指定延迟后执行
    T3】语法:

```java
public void schedule(TimerTask task, long delay)
Parameters:
task - task to be scheduled.
delay - delay in milliseconds before task is to be executed.
Throws:
IllegalArgumentException - if delay is negative,
or delay + System.currentTimeMillis() is negative.
IllegalStateException - if a task was already scheduled 
or cancelled, the timer was cancelled, 
or timer thread terminated.
NullPointerException - if task is null
```

*   **调度(TimerTask 任务，长延迟，长周期):Java . util . timer . schedule(time rtask 任务，长延迟，长周期)**调度指定任务重复固定延迟执行，在指定延迟后开始**语法:**

```java
public void schedule(TimerTask task, long delay, long period)
Parameters:
task - task to be scheduled.
delay - delay in milliseconds before task is to be executed.
period - time in milliseconds between successive task executions.
Throws:
IllegalArgumentException - if delay < 0, 
or delay + System.currentTimeMillis() < 0, or 
period <= 0
IllegalStateException - if task was already scheduled 
or cancelled, timer was cancelled, 
or timer thread terminated.
NullPointerException - if task is null
```

*   **scheduleatfixed rate(time rtask 任务，日期优先时间，长周期):Java . util . timer . scheduleatfixed rate(time rtask 任务，日期优先时间，长周期)**从指定的时间开始，调度指定的任务进行重复的固定速率执行**语法:**

```java
public void scheduleAtFixedRate(TimerTask task, Date firstTime, long period)
Parameters:
task - task to be scheduled.
firstTime - First time at which task is to be executed.
period - time in milliseconds between successive task executions.
Throws:
IllegalArgumentException - if firstTime.getTime() <
0 or period <= 0
IllegalStateException - if task was already scheduled
 or cancelled, timer was cancelled, 
or timer thread terminated.
NullPointerException - if task or firstTime is null
```

*   **scheduleatfixed rate(time rtask 任务，长延迟，长周期):Java . util . timer . scheduleatfixed rate(time rtask 任务，长延迟，长周期)**调度指定任务以重复固定速率执行，在指定延迟后开始**语法:**

```java
public void scheduleAtFixedRate(TimerTask task, long delay, long period)
Parameters:
task - task to be scheduled.
delay - delay in milliseconds before task is to be executed.
period - time in milliseconds between successive task executions.
Throws:
IllegalArgumentException - if delay < 0, 
or delay + System.currentTimeMillis() < 0, or 
period <= 0
IllegalStateException - if task was already 
scheduled or cancelled, timer was cancelled, 
or timer thread terminated.
NullPointerException - if task is null
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// scheduleAtFixedRate method of Timer class

import java.util.Timer;
import java.util.TimerTask;
import java.util.*;

class Helper extends TimerTask
{
    public static int i = 0;
    public void run()
    {
        System.out.println("Timer ran " + ++i);
        if(i == 4)
        {
            synchronized(Test.obj)
            {
                Test.obj.notify();
            }
        }
    }

}

public class Test
{
    protected static Test obj;
    public static void main(String[] args) throws InterruptedException
    {
        obj = new Test();

        //creating a new instance of timer class
        Timer timer = new Timer();
        TimerTask task = new Helper();

        //instance of date object for fixed-rate execution
        Date date = new Date();

        timer.scheduleAtFixedRate(task, date, 5000);

        System.out.println("Timer running");
        synchronized(obj)
        {
            //make the main thread wait
            obj.wait();

            //once timer has scheduled the task 4 times,
            //main thread resumes
            //and terminates the timer
            timer.cancel();

            //purge is used to remove all cancelled
            //tasks from the timer'stack queue
            System.out.println(timer.purge());
        }
    }
}
```

**输出:**

```java
Timer running
Timer ran 1
Timer ran 2
Timer ran 3
Timer ran 4
0
```

**参考:**

*   Oracle

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。