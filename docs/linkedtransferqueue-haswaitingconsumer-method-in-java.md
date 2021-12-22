# Java 中的 LinkedTransferQueue hasWaitingConsumer()方法

> 原文:[https://www . geeksforgeeks . org/linkedtransferqueue-haswaitingconsumer-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-haswaitingconsumer-method-in-java/)

**T1。如果队列中至少有一个使用者等待通过 BlockingQueue.take()或定时轮询接收元素，则 hasWaitingConsumer()** 方法始终返回 true。返回值表示事件的暂时状态。

**语法**

```java
public boolean hasWaitingConsumer()
```

**参数:**不取任何参数。

**返回值:**该方法返回**一个布尔值**，如果队列中至少有一个消费者，则该值为**真**。

下面是几个例子来说明 linkedtransferqueue . haswaitingconsumer()方法:

**例 1:**

```java
// Java code to demonstrate
// hasWaitingConsumer() method

import java.util.concurrent.LinkedTransferQueue;

class GFG {
    public static void main(String args[])
    {
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        LTQ.add("Geeks");
        LTQ.add("For");
        LTQ.add("Geeks");
        LTQ.add("GeeksForGeeks");

        System.out.println(LTQ.hasWaitingConsumer());
    }
}
```

**Output:**

```java
false

```

**例 2:**

```java
// Java code to demonstrate
// hasWaitingConsumer() method

import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.LinkedTransferQueue;

public class GFG {

    LinkedTransferQueue<Integer> LTQ
        = new LinkedTransferQueue<>();

    class LTQProducer implements Runnable {

        @Override
        public void run()
        {
            for (int i = 0; i < 3; i++) {
                try {
                    System.out.println("Producer is"
                                       + " waiting to transfer");
                    LTQ.transfer(i);
                    System.out.println("Producer transferred"
                                       + " element: "
                                       + i);
                    System.out.println("Is there any consumer"
                                       + " still waiting to"
                                       + " receive an element"
                                       + " after transfer -> "
                                       + LTQ.hasWaitingConsumer());
                }
                catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        }
    }

    class LTQConsumer implements Runnable {
        int id;
        LTQConsumer(int id)
        {
            this.id = id;
        }

        @Override
        public void run()
        {
            try {
                System.out.println("Consumer "
                                   + id
                                   + " is waiting to "
                                   + "take an element.");
                System.out.println("Is there any consumer"
                                   + " still waiting to"
                                   + " receive an element"
                                   + " after transfer -> "
                                   + LTQ.hasWaitingConsumer());
                Integer s = LTQ.take();
                System.out.println("Consumer "
                                   + id
                                   + " received Element: "
                                   + s);
            }
            catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }

    // Driver code
    public static void main(String[] args)
        throws InterruptedException
    {
        GFG ob = new GFG();

        ExecutorService exService
            = Executors.newFixedThreadPool(3);

        LTQProducer p = ob.new LTQProducer();
        LTQConsumer c1 = ob.new LTQConsumer(0);
        LTQConsumer c2 = ob.new LTQConsumer(1);

        exService.execute(p);
        exService.execute(c1);
        exService.execute(c2);

        exService.shutdown();
    }
}
```

**Output:**

> 生产者在等待转移
> 消费者 0 在等待拿一个元素。
> 有没有消费者等着拿元素- >假
> 消费者 1 等着拿元素。
> 是否有消费者等待领取要素- >假
> 消费者 0 领取要素:0
> 生产者转移要素:0
> 转移后是否还有消费者等待领取要素- >真
> 生产者等待转移
> 生产者转移要素:1
> 消费者 1 领取要素:1
> 转移后是否还有消费者等待领取要素- >假
> 生产者等待转移