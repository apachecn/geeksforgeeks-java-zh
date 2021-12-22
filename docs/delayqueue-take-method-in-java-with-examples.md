# Java 中的 DelayQueue take()方法，示例

> 原文:[https://www . geeksforgeeks . org/delay queue-take-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-take-method-in-java-with-examples/)

[延迟队列](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/)的 **take()** 方法用于检索延迟队列的头部并将其移除。因此，延迟队列的大小减小了。如果此队列中有延迟过期的元素，此函数将等待。
**语法:**

```
public E take ()
```

**参数:**该方法不接受参数。
**返回值:**该函数返回延迟队列的头部。
**异常:**如果在等待时被中断，此方法会抛出**中断异常**。
下面的程序说明了 DelayQueue.take()方法:
**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue take() method

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
        DQ.add(new DelayObject("C", 3));
        DQ.add(new DelayObject("D", 4));

        // print the size of DelayQueue
        System.out.println("Size of the DelayQueue: "
                           + DQ.size());
        // print queue
        System.out.println("DelayQueue: "
                           + DQ);

        // take() function will retrieve and remove the head of DelayQueue
        System.out.println("Head of the DelayQueue:"
                           + DQ.take());
        // print the size of DelayQueue
        System.out.println("Size of the DelayQueue: "
                           + DQ.size());
        // print queue
        System.out.println("DelayQueue: "
                           + DQ);
    }
}
```

**Output:** 

```
Size of the DelayQueue: 4
DelayQueue: [
{ A, time=1546842594283}, 
{ B, time=1546842594284}, 
{ C, time=1546842594285}, 
{ D, time=1546842594286}]
Head of the DelayQueue:
{ A, time=1546842594283}
Size of the DelayQueue: 3
DelayQueue: [
{ B, time=1546842594284}, 
{ D, time=1546842594286}, 
{ C, time=1546842594285}]
```