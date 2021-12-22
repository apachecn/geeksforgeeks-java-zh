# java 中的 Java . lang . management . threadinfo 类

> 原文:[https://www . geesforgeks . org/Java-lang-management-threadinfo-class-in-Java/](https://www.geeksforgeeks.org/java-lang-management-threadinfo-class-in-java/)

Java . lang . management . ThreadInfo 类包含获取线程信息的方法。这些信息包括:

*   线程标识
*   线程名称
*   线程的状态
*   线程的堆栈跟踪
*   线程被阻止的对象
*   线程阻止的对象监视器列表
*   被线程阻止的可拥有的同步器列表
*   线程被阻止的次数
*   线程被阻塞的时间

**语法:**类声明

```java
public class ThreadInfo
extends Object
```

此类的方法如下:

<figure class="table">

| way | describe |
| --- | --- |
| ThreadInfo from(复合数据) | This method is used to represent this composite data as a ThreadInfo object. |
| getBlockedCount() | This method is used to know how many times the thread associated with this ThreadInfo object is blocked from entering the monitor or re-entering the monitor. |
| getBlockedTime() | This method is used to know how many milliseconds the thread associated with this ThreadInfo object has been blocked from entering or re-entering the monitor. |
| getLockedMonitors() | This method is used to obtain the list of " *monitorinfo* " objects currently locked by the thread associated with this ThreadInfo object. |
| getlockedsynchronizer() | This method is used to obtain the list of synchronizers that *can own currently locked by the thread associated with this ThreadInfo object.* |
| 获取锁定信息（） | This method is used to get the information of the object whose thread associated with this ThreadInfo object is blocked from waiting. It returns a " *lock information* object representing information. |
| getlock name（） | This method is used to get the name of the object whose thread associated with this ThreadInfo object is blocked from waiting. |
| getLockOwnerId() | This method is used to get the Id of the thread that owns the object blocking this thread. |
| getlockwownername() | This method is used to get the name of the thread that owns the object blocking this thread. |
| getStackTrace() | This method is used to get the stack trace of a thread. |
| getThreadId() | This method is used to get the Id of a Thread. |
| getThreadName() | This method is used to get the name of a Thread. |
| getThreadState() | This method is used to get the status of a Thread. |
| getWaitedCount() | This method is used to know how many times the thread associated with this ThreadInfo object waits for notification. |
| getWaitedTime() | This method is used to know how many milliseconds the thread associated with this ThreadInfo object has been waiting for notification. |
| 是天生的() | This method is used to determine whether this ThreadInfo object is executing native code through java native interface. |
| issuespended() | This method is used to determine whether the thread associated with this ThreadInfo object is suspended. |
| toString() | This method is used to get the string representation of the given ThreadInfo object. |

</figure>

**实施:**

**示例 1:** 创建新的线程信息对象

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate ThreadInfo Class

// Importing required libraries
import java.lang.management.ManagementFactory;
import java.lang.management.ThreadInfo;

// Maij class
public class GFG {

    // main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            // Creating a new thread by
            // creating an object of Thread class
            Thread thread = new Thread();

            // running the thread using run() method
            thread.run();

            // Getting thread id using getId() method
            long id = thread.getId();

            // Creating a new ThreadInfo object
            // using that id
            ThreadInfo info
                = ManagementFactory.getThreadMXBean()
                      .getThreadInfo(id);

            // Print and display message on the console
            System.out.println(
                "ThreadInfo object created successfully");
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // print the line number where exception occurs
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
ThreadInfo object created successfully
```

**示例 2:** 使用 ThreadInfo 类的通用清理器线程

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate ThreadInfo Class

// Importing required libraries
import java.lang.management.ManagementFactory;
import java.lang.management.ThreadInfo;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // try block to check for exceptions
        try {

            long id = 10;

            // Creating a new ThreadInfo object
            // using this id
            ThreadInfo info
                = ManagementFactory.getThreadMXBean()
                      .getThreadInfo(id);
            // Printing information about the thread

            // 1\. Printing thread id
            System.out.println("Thread ID: "
                               + info.getThreadId());
            // 2\. Printing Thread Name
            System.out.println("Thread Name: "
                               + info.getThreadName());
            // 3\. Printing thread State
            System.out.println("Thread State: "
                               + info.getThreadState());
            // 4\. Printing thread waited count
            System.out.println("Waited count: "
                               + info.getWaitedCount());
            // 5\. Printing thread waited time
            System.out.println("Waited time: "
                               + info.getWaitedTime());
            // 6\. Printing how many times this thread had
            // been blocked
            System.out.println("Times blocked: "
                               + info.getBlockedCount());
            // 7\. Printing Blocked duration
            System.out.println("Blocked duration: "
                               + info.getBlockedTime());
            // 8\. Printing Locked Monitors
            System.out.println("Locked Monitors: "
                               + info.getLockedMonitors());
            // 9\. Printing Locked Owner's ID
            System.out.println("Locked Owner's ID: "
                               + info.getLockOwnerId());
            // 10\. Printing Locked Owner's Name
            System.out.println("Locked Owner's Name: "
                               + info.getLockOwnerName());
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the line number where exception occured
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Thread ID: 10
Thread Name: Common-Cleaner
Thread State: TIMED_WAITING
Waited count: 1
Waited time: -1
Times blocked: 0
Blocked duration: -1
Locked Monitors: [Ljava.lang.management.MonitorInfo;@15aeb7ab
Locked Owner's ID: -1
Locked Owner's Name: null
```