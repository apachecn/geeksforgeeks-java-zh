# Java 中的 Java.util.TimerTask 类

> 原文:[https://www . geesforgeks . org/Java-util-time rtask-class-Java/](https://www.geeksforgeeks.org/java-util-timertask-class-java/)

TimerTask 是 java.util 包中定义的抽象类。TimerTask 类定义了一个任务，该任务可以被安排为只运行一次，也可以重复运行多次。为了定义 TimerTask 对象，需要实现这个类，并且需要重写 run 方法。当定时器对象调度 run 方法时，run 方法被隐式调用。

**注意:**TimerTask 类的一个实例用于定义需要定期运行的任务。

**构造函数:**

*   **Timertask ()** : Create a new timer task.

**申报:**

```
public abstract class TimerTask
        extends Object
        implements Runnable
```

**方法:**

1.  **取消():Java . util . timertask . cancel()**取消此计时器任务

    **语法:**

    ```
    public boolean cancel()
    Returns:
    true if this task is scheduled for one-time execution and
    has not yet run, or this task is scheduled for repeated execution. 
    Returns false if the task was scheduled for one-time 
    execution and has already run, or if the task was never scheduled, 
    or if the task was already cancelled.
    ```

2.  **run():Java . util . timertask . run()**此计时器任务要执行的操作

    **语法:**

    ```
    public abstract void run()
    Description:
    The action to be performed by this timer task
    ```

3.  **scheduledExecutionTime():Java。乌提尔。timertask。预定执行**

**方法继承自 java.lang.Object 类**

*   clone
*   be equal to
*   verdict
*   getClass(获取类)
*   hashCode(哈希代码)
*   notifyAll(通知所有人)
*   tostring
*   wait for

**演示 TimerTask 类用法的 Java 程序**

```
// Java program to demonstrate 
// working of TimerTask class
import java.util.Timer;
import java.util.TimerTask;

class Helper extends TimerTask
{
    public static int i = 0;
    public void run()
    {
        System.out.println("Timer ran" + ++i);
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
    public static Test obj;
    public static void main(String[] args) throws InterruptedException
    {
        obj = new Test();

        // creating an instance of timer class
        Timer timer = new Timer();

        // creating an instance of task to be scheduled
        TimerTask task = new Helper();

        // scheduling the timer instance
        timer.schedule(task, 1000, 3000);

        // fetching the scheduled execution time of 
        // the most recent actual execution of the task
        System.out.println(task.scheduledExecutionTime());

        synchronized(obj)
        {
            //this thread waits until i reaches 4
            obj.wait();
        }

        //canceling the task assigned 
        System.out.println("Cancel the timer task: " + task.cancel());

        // at this point timer is still running 
        // without any task assigned to it

        // canceling the timer instance created
        timer.cancel();
    }
}
```

**输出:**

```
1495715853591
Timer ran 1
Timer ran 2
Timer ran 3
Timer ran 4
Cancel the timer task: true

```

**参考资料:**

*   [【Oracle】](https://docs.oracle.com/javase/8/docs/api/java/util/TimerTask.html)

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。