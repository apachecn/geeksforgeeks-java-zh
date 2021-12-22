# Java 中的 DelayQueue offer()方法，示例

> 原文:[https://www . geesforgeks . org/delay queue-offer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-offer-method-in-java-with-examples/)

[**延迟队列**](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/) 的 **offer()** 方法用于在延迟队列中插入指定元素。它的作用类似于 DelayQueue 的 add()方法。
**语法:**

```java
public boolean offer (E e)
```

**参数:**
延迟队列只接受属于延迟类型类的元素。所以，这个元素 E 应该是延迟的类型。
**返回:**
此方法不返回任何内容。
**异常:**
**空指针异常:**如果指定的元素为空。
下面程序来举例说明 DelayQueue offer()在 Java 中:
**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate DelayQueue offer() method

import java.util.concurrent.*;
import java.util.*;

// The DelayObject for DelayQueue
// It must implement Delayed and
// its getDelay() and compareTo() method
class DelayObject implements Delayed {

    private String name;
    private long time;

    // Constructor of DelayObject
    public DelayObject(String name, long delayTime)
    {
        this.name = name;
        this.time = System.currentTimeMillis()
                    + delayTime;
    }

    // Implementing getDelay() method of Delayed
    @Override
    public long getDelay(TimeUnit unit)
    {
        long diff = time - System.currentTimeMillis();
        return unit.convert(diff, TimeUnit.MILLISECONDS);
    }

    // Implementing compareTo() method of Delayed
    @Override
    public int compareTo(Delayed obj)
    {
        if (this.time < ((DelayObject)obj).time) {
            return -1;
        }
        if (this.time > ((DelayObject)obj).time) {
            return 1;
        }
        return 0;
    }

    // Implementing toString() method of Delayed
    @Override
    public String toString()
    {
        return "\n{"
            + " " + name + ", time=" + time + "}";
    }
}

// Driver Class
public class GFG {
    public static void main(String[] args) throws InterruptedException
    {

        // create object of DelayQueue
        // using DelayQueue() constructor
        BlockingQueue<DelayObject> DQ
            = new DelayQueue<DelayObject>();

        // Add numbers to end of DelayQueue
        // using add() method
        DQ.add(new DelayObject("A", 1));
        DQ.add(new DelayObject("B", 2));

        // Print delayqueue
        System.out.println("Original DelayQueue: "
                           + DQ + "\n");

        // Now insert elements using offer method
        DQ.offer(new DelayObject("C", 10));
        DQ.offer(new DelayObject("D", 11));
        DQ.offer(new DelayObject("E", 15));
        DQ.offer(new DelayObject("F", 17));

        // print queue
        System.out.println("After insertion DelayQueue: "
                           + DQ);
    }
}
```

**Output:** 

```java
Original DelayQueue: [
{ A, time=1545817395066}, 
{ B, time=1545817395067}]

After insertion DelayQueue: [
{ A, time=1545817395066}, 
{ B, time=1545817395067}, 
{ C, time=1545817395076}, 
{ D, time=1545817395077}, 
{ E, time=1545817395081}, 
{ F, time=1545817395083}]
```