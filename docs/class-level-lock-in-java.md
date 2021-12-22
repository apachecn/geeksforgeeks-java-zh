# Java 中的类级锁

> 原文:[https://www.geeksforgeeks.org/class-level-lock-in-java/](https://www.geeksforgeeks.org/class-level-lock-in-java/)

Java 中的每个类都有一个唯一的锁，这个锁就是 [**类级锁**](https://www.geeksforgeeks.org/object-level-class-level-lock-java/) 。如果一个线程想要执行一个静态同步方法，那么这个线程需要一个类级锁。类级锁防止多个线程在运行时进入该类的任何可用实例中的同步块。这意味着，如果在运行时一个类有 10 个实例，那么一次只有一个线程能够访问任何一个实例的一个方法或块。如果您想要保护静态数据，则使用它。

如果一个线程想要执行一个静态同步方法，那么这个线程需要一个类级锁。一旦线程获得了类级别的锁，那么它就被允许执行该类的任何静态同步方法。一旦方法执行完成，线程会自动释放锁。

**方法:**线程可以通过两种方法获取类级别的锁，即

1.  Use the synchronous static method.
2.  Adopt synchronous block.

**方法 1:** 使用同步静态方法

**实现:**我们有一个极客班。我们想用这个类的静态同步方法，线程一进入 synchronized 方法，线程就在类级别获取锁，其余线程等待获取类监视器锁。当线程从同步方法中退出时，它会留下一个锁。

```
public static synchronized int incrementCount()
{
}
```

**示例**

## Java

```
// Java program to illustrate class level lock

// Main Class
// Implememnting the Runnable interface
class Geek implements Runnable {

    // Method 1
    // @Override
    public void run() { Lock(); }

    // Method 2
    // Method is static
    public static synchronized void Lock()
    {
        // Gwetting the name of current thread by using
        // getName() method to get name of the thread and
        // currentThread() to get the current thread
        System.out.println(
            Thread.currentThread().getName());

        // class level lock
        synchronized (Geek.class)
        {
            System.out.println(
                "in block "
                + Thread.currentThread().getName());
            System.out.println(
                "in block "
                + Thread.currentThread().getName()
                + " end");
        }
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of above class
        // in the main() method
        Geek g1 = new Geek();

        // Sharing the same object across two Threads

        // Creating an object of thread class where
        // t1 takes g1
        Thread t1 = new Thread(g1);

        // Creating an object of thread class where
        // t2 takes g1
        Thread t2 = new Thread(g1);

        // Creating second object of above class
        // in the main() method
        Geek g2 = new Geek();

        // Creating an object of thread class where
        // t3 takes g2
        Thread t3 = new Thread(g2);

        // setName() method is used to set name to the
        // thread
        t1.setName("t1");
        t2.setName("t2");
        t3.setName("t3");

        // start() method is used for initiating the current
        // thread
        t1.start();
        t2.start();
        t3.start();
    }
}
```

**输出**

```
t1
in block t1
in block t1 end
t3
in block t3
in block t3 end
t2
in block t2
in block t2 end

```

输出解释:

线程 t1 进入静态同步方法，并持有 Geek 类的锁。因此，其余的线程等待线程 t1 释放极客类的锁，以便它可以进入静态同步方法。

**方法二:**采用同步阻断法

**实现:**我们有一个“极客”班。我们想创建一个同步块并传递类名。类作为参数告诉哪个类必须在类级别同步。一旦线程进入同步块，线程就获取类的锁，其余线程等待获取类监视器锁。当线程从同步块退出时，它将离开锁。

```
synchronized (Geek.class) {
    //thread has acquired lock on  Geek class
}
```

**例**

## 爪哇

```
// Java program to illustrate class level lock

// Main Class
// It is implementing the Runnable interface
class Geek implements Runnable {

    // Method 1
    // @Override
    public void run()
    {
        // Acquire lock on .class reference
        synchronized (Geek.class)

        // ClassName is name of the class containing method.
        {
            {
                System.out.println(
                    Thread.currentThread().getName());

                System.out.println(
                    "in block "
                    + Thread.currentThread().getName());
                System.out.println(
                    "in block "
                    + Thread.currentThread().getName()
                    + " end");
            }
        }

        // Method 2
        // Main driver method
        public static void main(String[] args)
        {
            // Creating an object of above class
            // in the main() method
            Geek g1 = new Geek();

            // Creating an object of thread class i.e Thread
            // 1 where t1 takes g1 object
            Thread t1 = new Thread(g1);
            // Here, creating Thread 2 where t2 takes g1
            // object
            Thread t2 = new Thread(g1); 

            // Creating another object of above class
            // in the main() method
            Geek g2 = new Geek();

            // Now reating Thread 3 where t3 takes g2 object
            Thread t3 = new Thread(g2);

            // Ginving custom names to above 3 threads
            // using the setName() method
            t1.setName("t1");
            t2.setName("t2");
            t3.setName("t3");

            // start() method is used to begin execution of
            // threads
            t1.start();
            t2.start();
            t3.start();
        }
    }
```

**输出:**

```
t1
in block t1
in block t1 end
t3
in block t3
in block t3 end
t2
in block t2
in block t2 end
```

输出解释:

线程 t1 进入同步块，并持有“极客”类的锁。因此，其余的线程等待线程 t1 释放“极客”类上的锁，以便它可以进入同步块。