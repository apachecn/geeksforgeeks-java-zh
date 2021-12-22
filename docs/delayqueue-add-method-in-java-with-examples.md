# Java 中的 DelayQueue add()方法，示例

> 原文:[https://www . geeksforgeeks . org/delay queue-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-add-method-in-java-with-examples/)

Java 中 DelayQueue 类的 **add(E ele)** 方法用于将给定元素插入延迟队列，如果元素已经成功插入，则返回 true。这里，E 指的是这个延迟队列集合维护的元素类型。
**语法** :

```java
public boolean add(E ele)
```

**参数:**该方法只取一个参数**元素**。它指的是将被插入延迟队列的元素。
**返回值:**如果元素添加成功，则返回值为真，否则返回假。
**异常:**

*   **空指针异常**:如果试图在这个延迟队列中插入一个空值，这个方法会抛出一个空指针异常。

下面的程序说明了 DelayQueue 类的 add()方法:
**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the add()
// method in Java

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create a DelayQueue instance
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Create an instance of Delayed
        Delayed obj = new Delayed() {
            public long getDelay(TimeUnit unit)
            {
                return 24; // some value is returned
            }

            public int compareTo(Delayed o)
            {
                if (o.getDelay(TimeUnit.DAYS) > this.getDelay(TimeUnit.DAYS))
                    return 1;
                else if (o.getDelay(TimeUnit.DAYS) == this.getDelay(TimeUnit.DAYS))
                    return 0;
                return -1;
            }
        };

        // Use the add() method to add obj to
        // the empty DelayQueue instance
        queue.add(obj);

        System.out.println("Size of the queue : " + queue.size());
    }
}
```

**Output:** 

```java
Size of the queue : 1
```

**程序 2** :演示空指针异常的程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the Exception
// thrown by add() method of
// DelayQueue classs

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create an instance of DelayQueue
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Try to add NULL to the queue
        try {
            queue.add(null);
        }

        // Catch Exception
        catch (Exception e) {

            // Print Exception raised
            System.out.println(e);
        }
    }
}
```

**Output:** 

```java
java.lang.NullPointerException
```