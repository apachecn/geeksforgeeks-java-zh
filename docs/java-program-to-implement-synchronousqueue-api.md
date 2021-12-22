# 实现同步队列 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-synchroniousqueue-API/](https://www.geeksforgeeks.org/java-program-to-implement-synchronousqueue-api/)

SynchronousQueue 是一个没有内部容量的特殊阻塞队列。它有助于以线程安全的方式在线程之间交换数据或信息。

**同步队列只有 2 个支持的操作:**

这两种方法都是阻塞方法，这意味着当我们想在队列中添加一条信息或数据时，我们调用 **put()** 方法，但该方法将保持阻塞状态，或者它将等待，直到其他线程调用 **take()** 方法，并允许该线程获取数据或信息。

1.**取()**

## Java 语言(一种计算机语言，尤用于创建网站)

```
try
{
  synchronousQueue.put("data or information goes here");
}

catch(InterruptedException iex)
{
  iex.printStackTrace();
}
```

2.**put()**

## Java

```
try
{
  // data type according to the data or information
  String info = synchronousQueue.take();
}

catch(InterruptedException iex)
{
  iex.printStackTrace();
}
```

基于两种不同访问策略的同步队列有两种类型的构造函数:

1. **SynchronousQueue():** 在这种情况下，如果多个线程正在等待，那么这些线程被随机或未指定的方式授予访问权限，这被称为无公平策略。

2.**同步队列(布尔公平):**在这种情况下，如果多个线程正在等待，则这些线程被授权以先进先出的方式访问。

**实现:**

T5】Java

```
// Java program to implement SynchronousQueue API.

import java.util.concurrent.BlockingQueue;
import java.util.concurrent.SynchronousQueue;

public class SynchronousQAPI<E> {

    public SynchronousQueue<E> synchronousQ;

    // we create a SynchronousQueue with no fair policy

    public SynchronousQAPI()
    {
        synchronousQ = new SynchronousQueue<E>();
    }

    // we create a SynchronousQueue with fair policy

    public SynchronousQAPI(boolean fair)
    {
        synchronousQ = new SynchronousQueue<E>();
    }

    // As we discussed above in API overview that
    // SynchronousQueue has 2 supported operations put() and
    // take() So, we will implement this methods only

    // put() method: It insert element at tail of the queue
    // and used to wait until the queue is full.

    public void put(E e) throws InterruptedException
    {
        synchronousQ.put(e);
    }

    // take() method: return element at the head of the
    // queue

    public E take() throws InterruptedException
    {
        return synchronousQ.take();
    }

    // Implementation of Put Thread (producer)
    class Put implements Runnable {

        @SuppressWarnings("rawtypes")
        BlockingQueue SynchronousQueue;

        @SuppressWarnings("rawtypes")
        public Put(BlockingQueue q)
        {
            this.SynchronousQueue = q;
        }

        @SuppressWarnings("unchecked")
        @Override
        public void run()
        {
            try {
                // put the data
                SynchronousQueue.put(1);
                System.out.println(
                    "1 added to synchronous queue.");
                Thread.sleep(1000);
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }

    class Take implements Runnable {
        @SuppressWarnings("rawtypes")
        BlockingQueue SynchronousQueue;

        @SuppressWarnings("rawtypes")
        public Take(BlockingQueue q)
        {
            this.SynchronousQueue = q;
        }

        @Override public void run()
        {
            try {
                // take out the previously inserted data
                this.SynchronousQueue.take();

                System.out.println(
                    "1 removed from synchronous queue.");
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }

    public static void main(String[] args)
        throws InterruptedException
    {
        SynchronousQAPI<Integer> synchronousQueue
            = new SynchronousQAPI<Integer>();

        new Thread(new SynchronousQAPI<>().new Put(
                       synchronousQueue.synchronousQ))
                       .start();

        new Thread(new SynchronousQAPI<>().new Take(
                       synchronousQueue.synchronousQ))
                       .start();
    }
}
```

**输出**

```
1 added to synchronous queue.
1 removed from synchronous queue.
```