# Java 中的 DelayQueue put()方法，示例

> 原文:[https://www . geeksforgeeks . org/delay queue-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-put-method-in-java-with-examples/)

Java 中 DelayQueue 类的 put(E ele)方法用于将给定的元素插入延迟队列容器中。E 是这个延迟队列容器维护的元素类型。

**语法**:

```java
public void put(E ele)
```

**参数:**该方法只接受一个参数**元素**。它是将被插入延迟队列的元素。
**返回值:**该方法的返回类型为 void，不返回值。
**异常:**

*   **NullPointRexception**:如果给定值为空，则抛出。

下面的程序说明了 Java 中 DelayQueue 的 put()方法:
**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the put()
// method in Java

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create DelayQueue instance
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Initially Delay Queue is empty
        System.out.println("Before calling put() : "
                           + queue.isEmpty());

        // Create an object of type Delayed
        Delayed ele = new Delayed() {
            public long getDelay(TimeUnit unit)
            {
                return 24; // some value is returned
            }

            public int compareTo(Delayed o)
            {
                if (o.getDelay(TimeUnit.DAYS) >
                              this.getDelay(TimeUnit.DAYS))
                    return 1;
                else if (o.getDelay(TimeUnit.DAYS) == 
                                this.getDelay(TimeUnit.DAYS))
                    return 0;
                return -1;
            }
        };

        // Insert the created object to DelayQueue
        // using the put() method
        queue.put(ele);

        // Check if DelayQueue is empty.
        System.out.println("After calling put() : "
                           + queue.isEmpty());
    }
}
```

**Output:** 

```java
Before calling put() : true
After calling put() : false
```

**程序 2**:NullPointerException 的演示。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the Exception thrown
// by put() method of DelayQueue

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        try {
            queue.put(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:** 

```java
java.lang.NullPointerException
```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/delayqueue . html # put(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/DelayQueue.html#put(E))