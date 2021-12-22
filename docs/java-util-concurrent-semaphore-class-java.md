# Java 中的 Java.util.concurrent.Semaphore 类

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-semaphore-class-Java/](https://www.geeksforgeeks.org/java-util-concurrent-semaphore-class-java/)

**先决条件:**[Java 中的信号量](https://www.geeksforgeeks.org/semaphore-in-java/)

```java
public class Semaphore
extends Object
implements Serializable
```

从概念上讲，信号量维护一组许可。如果需要，每个 acquire()都会阻塞，直到获得许可，然后再获取许可。每个 release()都会添加一个许可证，可能会释放一个阻塞的获取者。但是，没有使用实际的许可对象；信号量只是记录可用的数量，并相应地采取行动。
**方法:**

1.  **void acquire()** :此方法获取一个许可证，如果有许可证，立即返回，将可用许可证的数量减少一个。如果当前线程在等待许可时被中断，则会引发中断异常。

    ```java
    Syntax : 
    public void acquire() throws InterruptedException
    Parameters : 
    NA
    Returns :
    NA
    Throws:
    InterruptedException - if the current thread is interrupted

    ```

2.  **void acquire(int permissions)**:此方法获取给定数量的许可证(如果可用)，并立即返回，将可用许可证的数量减少给定的数量。如果当前线程在等待许可时被中断，则会引发中断异常。

    ```java
    Syntax : 
    public void acquire(int permits) throws InterruptedException
    Parameters : 
    permits - the number of permits to acquire
    Returns :
    NA
    Throws:
    InterruptedException - if the current thread is interrupted
    IllegalArgumentException - if permits is negative

    ```

3.  **void acquire continuously()**:此方法获取一个许可证，如果有许可证，立即返回，将可用许可证的数量减少一个。如果当前线程在等待许可时被中断，那么它将继续等待，

    ```java
    Syntax : 
    public void acquireUninterruptibly()
    Parameters : 
    NA
    Returns :
    NA

    ```

4.  **无效获取不间断(int permissions)**:该方法获取给定数量的许可证(如果可用)，并立即返回，将可用许可证的数量减少给定的数量。如果当前线程在等待许可时被中断，那么它将继续等待，

    ```java
    Syntax : 
    public void acquireUninterruptibly(int permits)
    Parameters : 
    permits - the number of permits to acquire
    Returns :
    NA
    Throws:
    IllegalArgumentException - if permits is negative

    ```

5.  **布尔型 tryAcquire()** :这个方法获取一个许可，如果有许可，立即返回，值为 true，将可用许可的数量减少一个。如果没有可用的许可，则该方法将立即返回 false 值。

    ```java
    Syntax : 
    public boolean tryAcquire()
    Parameters : 
    NA
    Returns :
    true if a permit was acquired and false otherwise

    ```

6.  **boolean try acquire(int permissions)**:此方法获取给定数量的许可证(如果可用)，并立即返回，值为 true，将可用许可证的数量减少给定的数量。如果没有足够的许可，那么这个方法将立即返回 false 值。

    ```java
    Syntax : 
    public boolean tryAcquire(int permits)
    Parameters : 
    permits - the number of permits to acquire
    Returns :
    true if the permits were acquired and false otherwise
    Throws:
    IllegalArgumentException - if permits is negative

    ```

7.  **布尔型 tryAcquire(长超时，时间单位单位)**:此方法获取一个许可，如果有许可，立即返回，值为 true，将可用许可的数量减少一个。如果经过了指定的等待时间，则返回值 false。如果时间小于或等于零，则该方法根本不会等待。

    ```java
    Syntax : 
    public boolean tryAcquire(long timeout, TimeUnit unit)
         throws InterruptedException
    Parameters : 
    timeout - the maximum time to wait for a permit
    unit - the time unit of the timeout argument
    Returns :
    true if a permit was acquired and 
    false if the waiting time elapsed before a permit was acquired
    Throws:
    InterruptedException - if the current thread is interrupted

    ```

8.  **布尔型 try acquire(int permissions，long timeout，TimeUnit unit)** :该方法获取给定数量的许可，如果许可可用，则立即返回，值为 true，将可用许可数量减少给定数量。如果经过了指定的等待时间，则返回值 false。如果时间小于或等于零，则该方法根本不会等待。任何要分配给这个线程的许可都被分配给试图获取许可的其他线程。

    ```java
    Syntax : 
    public boolean tryAcquire(int permits, long timeout, TimeUnit unit) 
    throws InterruptedException
    Parameters : 
    permits - the number of permits to acquire
    timeout - the maximum time to wait for a permit
    unit - the time unit of the timeout argument
    Returns :
    true if all permits were acquired and 
    false if the waiting time elapsed before all 
    permits were acquired
    Throws:
    InterruptedException - if the current thread is interrupted
    IllegalArgumentException - if permits is negative

    ```

9.  **无效释放()**:此方法释放一个许可证，将可用的许可证数量增加一个。如果有任何线程试图获取一个许可，那么就选择一个线程，并给它刚刚发布的许可。

    ```java
    Syntax : 
    public void release()
    Parameters : 
    NA
    Returns :
    NA

    ```

10.  **无效释放(int permissions)**:该方法释放给定数量的许可证，将可用许可证的数量增加该数量。如果有任何线程试图获取许可，那么就选择一个线程，并给予刚刚释放的许可。如果可用许可的数量满足该线程的请求，则该线程被(重新)启用用于线程调度目的；否则，线程将等待，直到有足够的许可可用。

    ```java
    Syntax : 
    public void release(int permits)
    Parameters : 
    permits - the number of permits to release
    Returns :
    NA
    Throws : 
    IllegalArgumentException - if permits is negative

    ```

11.  **int availablePermits()** :这个方法返回这个信号量中当前可用的许可数量。此方法通常用于调试和测试目的。

    ```java
    Syntax : 
    public int availablePermits()
    Parameters : 
    NA
    Returns :
    the number of permits available in this semaphore

    ```

12.  **int drawing licenses()**:这个方法获取并返回所有立即可用的许可。

    ```java
    Syntax : 
    public int drainPermits()
    Parameters : 
    NA
    Returns :
    the number of permits acquired

    ```

13.  **void reduced permissions(int reduction)**:此方法通过指定的缩减来缩减可用许可的数量。这种方法在使用信号量跟踪变得不可用的资源的子类中非常有用。这种方法不同于获取，因为它不阻止等待许可变得可用。

    ```java
    Syntax : 
    protected void reducePermits(int reduction)
    Parameters : 
    reduction - the number of permits to remove
    Returns :
    NA
    Throws :
    IllegalArgumentException - if reduction is negative

    ```

14.  **布尔 isFair()** :如果这个信号量的公平性设置为真，这个方法返回真。

    ```java
    Syntax : 
    public boolean isFair()
    Parameters : 
    NA
    Returns :
    true if this semaphore has fairness set true

    ```

15.  **最终布尔 hasQueuedThreads()** :这个方法查询是否有线程在等待获取。请注意，因为取消可能随时发生，所以真正的返回并不能保证任何其他线程会获得。这种方法主要用于监控系统状态。

    ```java
    Syntax : 
    public final boolean hasQueuedThreads()
    Parameters : 
    NA
    Returns :
    true if there may be other threads waiting to acquire the lock

    ```

16.  **final int getQueueLength()** :这个方法返回等待获取的线程数的估计值。该值只是一个估计值，因为当此方法遍历内部数据结构时，线程的数量可能会动态变化。这种方法设计用于监控系统状态，而不是用于同步控制。

    ```java
    Syntax : 
    public final int getQueueLength()
    Parameters : 
    NA
    Returns :
    the estimated number of threads waiting for this lock

    ```

17.  **集合 <thread>getQueuedThreads()</thread>** :这个方法返回一个包含可能正在等待获取的线程的集合。因为实际的线程集合在构造这个结果时可能会动态变化，所以返回的集合只是尽力而为的估计。返回集合的元素没有特定的顺序。

    ```java
    Syntax : 
    protected Collection getQueuedThreads()
    **Parameters :** 
    NA
    **Returns :**
    the collection of threads 
    ```

18.  **字符串 toString()** :这个方法返回一个标识这个信号量及其状态的字符串。括号中的状态包括字符串“许可证=”，后跟许可证数量。

    ```java
    Syntax : 
    public String toString()
    Parameters : 
    NA
    Returns :
    a string identifying this semaphore, as well as its state
    Overrides:
    toString in class Object

    ```

**示例说明方法:**注意输出不是一直都一样的。

```java
// Java program to demonstrate 
// methods of Semaphore class
import java.util.concurrent.*;

class MyThread extends Thread
{
    Semaphore sem;
    String threadName;
    public MyThread(Semaphore sem, String threadName) 
    {
        super(threadName);
        this.sem = sem;
        this.threadName = threadName;
    }

    @Override
    public void run() {

            // First, get a permit.
            System.out.println(threadName + " is waiting for a permit.");

               try {
                 // acquire method
                sem.acquire();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }

               System.out.println(threadName + " gets a permit");

            // Now, critical section
            // other waiting threads will wait, until this
               // thread release the lock
            for(int i=0; i < 2; i++)
            {
                 // hasQueuedThreads() methods
                 boolean b = sem.hasQueuedThreads();
                 if(b)
                     // getQueuedLength() methods
                     System.out.println("Length of Queue : " + sem.getQueueLength())    ;

                 // Now, allowing a context switch -- if possible.
                 try {
                    Thread.sleep(10);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }

            // Release the permit.
            System.out.println(threadName + " releases the permit.");

            // release() method
            sem.release();
        }
}

// Driver class
public class SemaphoreDemo 
{

    public static void main(String args[]) throws InterruptedException 
    {
        // creating a Semaphore object
        // with number of permits 3 and fairness true
        Semaphore sem = new Semaphore(3, true);

        //isFair() method 
        System.out.println("is Fairness enabled : " + sem.isFair());

        // Main thread try to acquire 2 permits
        // tryAcquire(int permits) method
        sem.tryAcquire(2);

        // availablePermits() method
        System.out.println("Available permits : " + sem.availablePermits());

        //drainPermits() method
        System.out.println("number of permits drain by Main thread : " 
                                      + sem.drainPermits());

        // permit released by Main thread
        sem.release(1);

        // creating two threads with name A and B
        MyThread mt1 = new MyThread(sem, "A");
        MyThread mt2 = new MyThread(sem, "B");

        // starting threads A
        mt1.start();

        // starting threads B
        mt2.start();

        // toString method
        System.out.println(sem.toString());

        // waiting for threads A and B 
        mt1.join();
        mt2.join();
    }
}
```

输出:

```java
is Fairness enabled : true
Available permits : 1
number of permits drain by Main thread : 1
java.util.concurrent.Semaphore@7852e922[Permits = 1]
B is waiting for a permit.
B gets a permit
A is waiting for a permit.
Length of Queue : 1
B releases the permit.
A gets a permit
A releases the permit.

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。