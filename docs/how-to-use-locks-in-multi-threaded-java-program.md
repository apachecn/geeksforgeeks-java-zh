# 多线程 Java 程序中如何使用锁？

> 原文:[https://www . geesforgeks . org/如何使用多线程 java 程序锁/](https://www.geeksforgeeks.org/how-to-use-locks-in-multi-threaded-java-program/)

锁可能是比标准同步块更灵活和复杂的线程同步机制。锁可以是用于控制多个线程对共享资源的访问的工具。通常，锁提供对共享资源的独占访问:一次只有一个线程可以获取锁，每个访问共享资源的人都需要先获取锁。然而，有些锁可能允许对共享资源的并发访问，比如读写锁的读锁。

```java
// Example of lock interface
Lock lock = new ReentrantLock();
lock.lock();

// critical section 
lock.unlock();
```

**锁定界面中的方法**

锁接口中有某些方法。我们将查看那些以及它们的修饰符:

<figure class="table">–它试图立即累积锁，如果锁定成功则返回 true

| **[modifier]** | **Description** |
| --- | --- |
| 空的 | Lock ()–If the lock is available, it will acquire the lock; If the lock is not available, the thread will be blocked until the lock is released. |
| Lock Intermittent ()–It is similar to lock (), but it will acquire the lock unless the thread is interrupted. |
| Unlock ()–as the name implies, it is just an instance of releasing the lock. |
| condition | New condition ()–It just returns a new condition instance. |
| boolean type |
| TryLock (time unit unit)–it is usually almost the same as try Lock (), except that it waits for a given timeout before giving up trying to accumulate locks. |

</figure>

**锁的实施**

让我们看看如何在 Java 中实现一些锁:

[T2【1 .读写锁()T4](https://www.geeksforgeeks.org/readwritelock-interface-in-java/#:~:text=A%20java.util.concurrent.,resource%20without%20causing%20concurrency%20errors.)

```java
ReadWriteLock readWriteLock = new ReentrantReadWriteLock();

readWriteLock.readLock().lock();

    // ....

                ......//

readWriteLock.readLock().unlock();

readWriteLock.writeLock().lock();

    // only one writer can enter this section,
    // and only if no threads are currently reading.

readWriteLock.writeLock().unlock();
```

下面是 readWriteLock()方法的实现:

T3】JavaT5

```java
// Implementation of ReadWriteLock in Java
import java.io.*;
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReadWriteLock;
import java.util.concurrent.locks.ReentrantReadWriteLock;
class GFG<O> {

    private final ReadWriteLock readWriteLock
        = new ReentrantReadWriteLock();
    private final Lock writeLock
        = readWriteLock.writeLock();
    private final Lock readLock = readWriteLock.readLock();
    private final List<O> list = new ArrayList<>();

    // setElement function sets
    // i.e., write the element to the thread
    public void setElement(O o)
    {
        // acquire the thread for writing
        writeLock.lock();
        try {
            list.add(o);
            System.out.println(
                "Element by thread "
                + Thread.currentThread().getName()
                + " is added");
        }
        finally {
            // To unlock the acquired write thread
            writeLock.unlock();
        }
    }

    // getElement function prints
    // i.e., read the element from the thread
    public O getElement(int i)
    {
        // acquire the thread for reading
        readLock.lock();
        try {
            System.out.println(
                "Elements by thread "
                + Thread.currentThread().getName()
                + " is printed");
            return list.get(i);
        }
        finally {
            // To unlock the acquired read thread
            readLock.unlock();
        }
    }
    public static void main(String[] args)
    {
        GFG<String> gfg = new GFG<>();

        gfg.setElement("Hi");
        gfg.setElement("Hey");
        gfg.setElement("Hello");

        System.out.println("Printing the last element : "
                           + gfg.getElement(2));
    }
}
```

T6T8**输出**T1

[**2。重入锁定()**](https://www.geeksforgeeks.org/reentrant-lock-java/)

```java
public class lockImplement {
    //...
    ReentrantLock lock = new ReentrantLock();
    int counter = 0;

    public void testing() {
        lock.lock();
        try {
            // Critical section here
            count++;
        } finally {
            lock.unlock();
        }
    }
    //...
}
```

下面是重入锁()方法的实现:

## Java

T0T6】

**输出:**

```java
task name - Job2 waiting for lock
task name - Job1 outer lock acquired at 09:49:42 Doing outer work
task name - Job2 waiting for lock
task name - Job1 inner lock acquired at 09:49:44 Doing inner work
Lock Hold Count - 2
task name - Job2 waiting for lock
task name - Job2 waiting for lock
task name - Job1 releasing inner lock
Lock Hold Count - 1
task name - Job1 work done
task name - Job1 releasing outer lock
Lock Hold Count - 0
task name - Job3 outer lock acquired at 09:49:45 Doing outer work
task name - Job2 waiting for lock
task name - Job3 inner lock acquired at 09:49:47 Doing inner work
Lock Hold Count - 2
task name - Job2 waiting for lock
task name - Job2 waiting for lock
task name - Job3 releasing inner lock
Lock Hold Count - 1
task name - Job3 work done
task name - Job3 releasing outer lock
Lock Hold Count - 0
task name - Job4 outer lock acquired at 09:49:48 Doing outer work
task name - Job2 waiting for lock
task name - Job4 inner lock acquired at 09:49:50 Doing inner work
Lock Hold Count - 2
task name - Job2 waiting for lock
task name - Job2 waiting for lock
task name - Job4 releasing inner lock
Lock Hold Count - 1
task name - Job4 work done
task name - Job4 releasing outer lock
Lock Hold Count - 0
task name - Job2 outer lock acquired at 09:49:52 Doing outer work
task name - Job2 inner lock acquired at 09:49:53 Doing inner work
Lock Hold Count - 2
task name - Job2 releasing inner lock
Lock Hold Count - 1
task name - Job2 work done
task name - Job2 releasing outer lock
Lock Hold Count - 0
```

**注意:**由于睡眠调用，程序可能无法在在线 IDE 上工作。