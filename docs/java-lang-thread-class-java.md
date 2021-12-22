# Java 中的 Java.lang.Thread 类

> 原文:[https://www.geeksforgeeks.org/java-lang-thread-class-java/](https://www.geeksforgeeks.org/java-lang-thread-class-java/)

在程序中执行一行代码。每个程序可以有多个关联的线程。每个线程都有一个优先级，线程调度器使用该优先级来确定哪个线程必须首先运行。Java 提供了一个线程类，它有各种各样的方法调用，以便通过提供构造函数和方法来对线程执行操作，从而管理线程的行为。

![](img/ec856a2d1fa1aac0d735f767e92a82bb.png)

**创建线程的方式**

1.  创建扩展到父线程类的自己的类
2.  实现可运行的接口。

下面是伪代码，你可以参考它们来更好地了解线程。

插图 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Way 1
// Creating thread By Extending To Thread class

class MyThread extends Thread {

    // Method 1
    // Run() method for our thread
    public void run()
    {

        // Print statement
        System.out.println(
            "Thread is running created by extending to parent Thread class");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of our thread class inside main()
        // method
        MyThread myThread = new MyThread();

        // Starting the thread
        myThread.start();
    }
}
```

**Output**

```java
Thread is running created by extending to parent Thread class
```

**插图 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Way 2
// Creating thread using Runnable interface

class ThreadUsingInterface implements Runnable {

    // Method 1
    // run() method for the thread
    public void run()
    {

        // Print statement
        System.out.println("Thread is created using Runnable interface");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of our thread class inside main()
        // method
        ThreadUsingInterface obj = new ThreadUsingInterface();

        // Passign the object to thread in main()
        Thread myThread = new Thread(obj);

        // Starting the thread
        myThread.start();
    }
}
```

**Output**

```java
Thread is created using Runnable interface
```

### Java 中的线程类

线程是一个程序，它以一个在这个类中经常使用的方法()开始，这个方法就是 start()方法。这个方法寻找 run()方法，它也是这个类的一个方法，并开始执行 run()方法的 bod。这里要注意 sleep()方法，这将在后面讨论。

> **注意:**每个被用作线程的类都必须实现 Runnable 接口，并覆盖它的 run 方法。

**语法:**

```java
public class Thread extends Object implements Runnable
```

### 该类的构造函数如下:

<figure class="table">

| 构造器 | 已执行的操作 |
| --- | --- |
| 螺纹() | 分配一个新的线程对象。 |
| 线程(可运行目标) | 分配一个新的线程对象。 |
| 线程(可运行目标，字符串名称) | 分配一个新的线程对象。 |
| 线程(字符串名称) | 分配一个新的线程对象。 |
| 线程(线程组组，可运行目标) | 分配一个新的线程对象。 |
| 线程(线程组组、可运行目标、字符串名称) | 分配一个新的线程对象，使其作为运行对象，以指定的名称作为名称，并属于组引用的线程组。 |
| 线程(线程组组、可运行目标、字符串名称、长堆栈大小) | 分配一个新的线程对象，使其作为运行对象，以指定的名称作为名称，属于组引用的线程组，并具有指定的堆栈大小。 |
| 线程(线程组组，字符串名称) | 分配一个新的线程对象。 |

</figure>

### 线程类的方法:

现在让我们来讨论一下这个类的所有**方法**如下所示:

<figure class="table">

| 方法 | 已执行的操作 |
| --- | --- |
| 活动计数() | 返回当前线程的线程组及其子组中活动线程数量的估计值 |
| checkAccess() | 确定当前运行的线程是否有权修改此线程 |
| 克隆() | 引发克隆支持异常，因为线程不能被有意义地克隆 |
| 电流线程() | 返回对当前正在执行的线程对象的引用 |
| [dumpStack()](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 将当前线程的堆栈跟踪打印到标准错误流 |
| 枚举(线程[] tarray) | 将当前线程的线程组及其子组中的每个活动线程复制到指定数组中 |
| [getAllStackTraces（）](https://www.geeksforgeeks.org/how-to-display-all-running-threads-in-java/) | 返回所有活动线程的堆栈跟踪图 |
| [getContextClassLoader()](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 返回此线程的上下文类加载器 |
| [get default unchechtxceptionhandler()](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 返回当线程由于未捕获的异常而突然终止时调用的默认处理程序 |
| [getId()](https://www.geeksforgeeks.org/how-to-get-the-id-of-a-current-running-thread-in-java/#:~:text=The%20getId()%20method%20of,thread%20ID%20may%20be%20reused.) | 返回此线程的标识符 |
| [获取名称（）](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/) | 返回此线程的名称 |
| [getPriority()](https://www.geeksforgeeks.org/java-thread-priority-multithreading/) | 返回此线程的优先级 |
| [getStackTrace（）](https://www.geeksforgeeks.org/java-lang-stacktraceelement-class-java/) | 返回表示此线程的堆栈转储的堆栈跟踪元素数组 |
| [getState（）](https://www.geeksforgeeks.org/lifecycle-and-states-of-a-thread-in-java/) | 返回此线程的状态 |
| [getThreadGroup()](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 返回该线程所属的线程组 |
| [获取 ncaughtExceptionHandler()](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 返回当此线程由于未捕获的异常而突然终止时调用的处理程序 |
| [保持锁定(对象对象)](https://www.geeksforgeeks.org/how-to-check-if-a-thread-holds-lock-on-a-particular-object-in-java/) | 当且仅当当前线程持有指定对象的监视器锁时，返回 true |
| [中断()](https://www.geeksforgeeks.org/how-a-thread-can-interrupt-an-another-thread-in-java/) | 中断这个线程 |
| 中断() | 测试当前线程是否已被中断 |
| [isAlive()](https://www.geeksforgeeks.org/isalive-and-join-methods-of-thread-class-in-java/) | 测试这个线程是否是活动的 |
| [【isdaemon()](https://www.geeksforgeeks.org/daemon-thread-java/) | 测试该线程是否是守护线程 |
| isInterrupted() | 测试此线程是否已被中断 |
| [join()](https://www.geeksforgeeks.org/isalive-and-join-methods-of-thread-class-in-java/) | 等待该线程死亡 |
| [加入(长毫)](https://www.geeksforgeeks.org/joining-threads-in-java/#:~:text=join(long%20millis)%20%3AIt,for%20specified%20time%20(milliseconds).&text=join(long%20millis%2C%20int%20nanos,time%20(milliseconds%20%2B%20nanos).) | 等待此线程死亡的时间最多为毫秒 |
| [运行()](https://www.geeksforgeeks.org/difference-between-thread-start-and-thread-run-in-java/) | 如果这个线程是用一个单独的 Runnable run 对象构造的，那么调用该 Runnable 对象的 run 方法；否则，此方法不执行任何操作并返回 |
| [setContextClassLoader(类加载器 cl)](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 为此线程设置上下文类加载器 |
| [setDaemon(boolean on)](https://www.geeksforgeeks.org/daemon-thread-java/) | 将此线程标记为守护程序线程或用户线程 |
| setdefaultunchechtxceptionhandler(线程)。uncaughtexceptionhandler eh) | 设置当线程由于未捕获的异常而突然终止，并且没有为该线程定义其他处理程序时调用的默认处理程序 |
| [设置名称（字符串名称）](https://www.geeksforgeeks.org/naming-thread-fetching-name-current-thread-java/) | 将此线程的名称更改为等于参数名称。 |
| setuncaughtexceptionhandler(线程)。uncaughtexceptionhandler eh) | 设置当此线程由于未捕获的异常而突然终止时调用的处理程序 |
| [设置优先级(int newPriority)](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 更改此线程的优先级 |
| [睡眠(长毫)](https://www.geeksforgeeks.org/java-concurrency-yield-sleep-and-join-methods/) | 使当前正在执行的线程休眠(暂时停止执行)指定的毫秒数，这取决于系统计时器和调度程序的精度和准确性 |
| [start()](https://www.geeksforgeeks.org/java-program-to-create-a-thread/) | 导致此线程开始执行；Java 虚拟机调用这个线程的运行方法 |
| [toString()](https://www.geeksforgeeks.org/java-lang-thread-class-java/) | 返回此线程的字符串表示形式，包括线程的名称、优先级和线程组 |
| [产量()](https://www.geeksforgeeks.org/java-concurrency-yield-sleep-and-join-methods/) | 给调度程序的提示，当前线程愿意让出它当前对处理器的使用 |

</figure>

还要记住，有一些**方法是从 java 类继承的。** **郎。对象如下:**

1.  *等于()方法*
2.  [*敲定()方法*](https://www.geeksforgeeks.org/finalize-method-in-java-and-how-to-override-it/)
3.  *getClass()方法*
4.  *hashCode()方法*
5.  [*通知()方法*](https://www.geeksforgeeks.org/java-notify-method-in-threads-synchronization-with-examples/)
6.  [*通知法*](https://www.geeksforgeeks.org/difference-notify-notifyall-java/)
7.  [*toString()方法*](https://www.geeksforgeeks.org/java-lang-thread-class-java/)
8.  [等待()方法](https://www.geeksforgeeks.org/wait-method-in-java-with-examples/)

**示例:**演示 Thread 类用法的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program Demonstrating Methods of Thread class

// Importing package
package generic;

// Class 1
// Helper class implementing Runnable interface
class Helper implements Runnable {

    //
    public void run() {

        // Try block to check for exceptions
        try {

            // Print statement
            System.out.println("thread2 going to sleep for 5000");

            // Making thread sleep for 0.5 seconds
            Thread.sleep(5000);

        }

        // Catch block to handle exception
        catch (InterruptedException e) {

            // Print statement
            System.out.println("Thread2 interrupted");
        }
    }
}

// Class 2
// Helper class extensing Runnable interface
public class Test implements Runnable {

    // Method 1
    // run() method of this class
    public void run() {

        // Thread run() method
    }

    // Method 2
    // Main driver method
    public static void main(String[] args) {

        // Making objects of class 1 and 2 in main() method
        Test obj = new Test();
        Helper obj2 = new Helper();

        // Creating 2 threads in main() method
        Thread thread1 = new Thread(obj);
        Thread thread2 = new Thread(obj2);

        // Moving thread to runnable states
        thread1.start();
        thread2.start();

        // Loading thread 1 in class 1
        ClassLoader loader = thread1.getContextClassLoader();

        // Creating 3rd thread in main() method
        Thread thread3 = new Thread(new Helper());

        // Getting number of active threads
        System.out.println(Thread.activeCount());
        thread1.checkAccess();

        // Fetching an instance of this thread
        Thread t = Thread.currentThread();

        // Print and display commands
        System.out.println(t.getName());

        System.out.println("Thread1 name: " + thread1.getName());
        System.out.println("Thread1 ID: " + thread1.getId());

        // Fetching the priority and state of thread1
        System.out.println("Priority of thread1 = " + thread1.getPriority());

        // Getting th state of thread 1 using getState() method
        // and printing the same
        System.out.println(thread1.getState());

        thread2 = new Thread(obj2);
        thread2.start();
        thread2.interrupt();
        System.out.println("Is thread2 interrupted? " + thread2.interrupted() );
        System.out.println("Is thread2 alive? " + thread2.isAlive());

        thread1 = new Thread(obj);
        thread1.setDaemon(true);
        System.out.println("Is thread1 a daemon thread? " + thread1.isDaemon());
        System.out.println("Is thread1 interrupted? " + thread1.isInterrupted());

        // Waiting for thread2 to complete its execution
        System.out.println("thread1 waiting for thread2 to join");

        try {
            thread2.join();
        }

        catch (InterruptedException e) {

            // Display the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Now setting the name of thread1
        thread1.setName("child thread xyz");

        // Print and display command
        System.out.println("New name set for thread 1" + thread1.getName());

        // Setting the priority of thread1
        thread1.setPriority(5);

        thread2.yield();

        // Fetching the string representation of thread1
        System.out.println(thread1.toString());

        // Getting list of active thread in current thread's group
        Thread[] tarray = new Thread[3];

        Thread.enumerate(tarray);

        // Display commands
        System.out.println("List of active threads:");
        System.out.printf("[");

        // Looking out using for each loop
        for (Thread thread : tarray) {

            System.out.println(thread);
        }

        // Display commands
        System.out.printf("]\n");

        System.out.println(Thread.getAllStackTraces());

        ClassLoader classLoader = thread1.getContextClassLoader();
        System.out.println(classLoader.toString());
        System.out.println(thread1.getDefaultUncaughtExceptionHandler());

        thread2.setUncaughtExceptionHandler(thread1.getDefaultUncaughtExceptionHandler());
        thread1.setContextClassLoader(thread2.getContextClassLoader());
        thread1.setDefaultUncaughtExceptionHandler(thread2.getUncaughtExceptionHandler());

        thread1 = new Thread(obj);
        StackTraceElement[] trace = thread1.getStackTrace();

        System.out.println("Printing stack trace elements for thread1:");

        for (StackTraceElement e : trace) {
            System.out.println(e);
        }

        ThreadGroup grp = thread1.getThreadGroup();
        System.out.println("ThreadGroup to which thread1 belongs " + grp.toString());
        System.out.println(thread1.getUncaughtExceptionHandler());
        System.out.println("Does thread1 holds Lock? " + thread1.holdsLock(obj2));

        Thread.dumpStack();

    }
}
```

**输出:**

```java
3
main
Thread1 name: Thread-0
Thread1 ID: 10
Priority of thread1 = 5
RUNNABLE
Is thread2 interrupted? false
Is thread2 alive? true
Is thread1 a daemon thread? true
Is thread1 interrupted? false
thread1 waiting for thread2 to join
thread2 going to sleep for 5000 ms
thread2 going to sleep for 5000 ms
Thread2 interrupted
New name set for thread 1child thread xyz
Thread[child thread xyz, 5, main]
List of active threads:
[Thread[main, 5, main]
Thread[Thread-1, 5, main]
null
]
{Thread[Signal Dispatcher, 9, system]=[Ljava.lang.StackTraceElement;@33909752, 
Thread[Thread-1, 5, main]=[Ljava.lang.StackTraceElement;@55f96302, 
Thread[main, 5, main]=[Ljava.lang.StackTraceElement;@3d4eac69, 
Thread[Attach Listener, 5, system]=[Ljava.lang.StackTraceElement;@42a57993, 
Thread[Finalizer, 8, system]=[Ljava.lang.StackTraceElement;@75b84c92, 
Thread[Reference Handler, 10, system]=[Ljava.lang.StackTraceElement;@6bc7c054}
sun.misc.Launcher$AppClassLoader@73d16e93
null
Printing stack trace elements for thread1:
ThreadGroup to which thread1 belongs java.lang.ThreadGroup[name=main, maxpri=10]
java.lang.ThreadGroup[name=main, maxpri=10]
Does thread1 holds Lock? false
java.lang.Exception: Stack trace
    at java.lang.Thread.dumpStack(Unknown Source)
    at generic.Test.main(Test.java:111) 
```

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。