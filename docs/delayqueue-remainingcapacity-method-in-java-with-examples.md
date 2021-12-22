# Java 中的 DelayQueue remainingCapacity()方法，示例

> 原文:[https://www . geeksforgeeks . org/delay queue-remainingcapacity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-remainingcapacity-method-in-java-with-examples/)

[延迟队列](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/)的**剩余空间()**方法总是返回**整数。最大值**因为延迟队列不受容量限制。这意味着，不管延迟队列的大小如何，它都会返回相同的结果，即整数。最大值。

**语法:**

```
public int remainingCapacity ()
```

**返回值:**函数返回**整数。最大值**。
**异常:**无异常。

下面的程序说明了 DelayQueue.remainingCapacity()方法:

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue remainingCapacity() method

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

        // print the size of DelayQueue
        System.out.println("Size of the DelayQueue: "
                           + DQ.size());

        // remainingCapacity() method always returns Integer.MAX_VALUE
        System.out.println("DelayQueue Remaining Capacity:"
                           + DQ.remainingCapacity());
        // poll() method for removing head of the DelayQueue
        DQ.poll();
        // print the size of DelayQueue
        System.out.println("Size of the DelayQueue: "
                           + DQ.size());
        // remainingCapacity() method always returns Integer.MAX_VALUE
        System.out.println("DelayQueue Remaining Capacity:"
                           + DQ.remainingCapacity());
        // poll() method for removing head of the DelayQueue
        DQ.poll();
        // print the size of DelayQueue
        System.out.println("Size of the DelayQueue: "
                           + DQ.size());
        // remainingCapacity() method always returns Integer.MAX_VALUE
        System.out.println("DelayQueue Remaining Capacity:"
                           + DQ.remainingCapacity());
    }
}
```

**Output:** 

```
Size of the DelayQueue: 2
DelayQueue Remaining Capacity:2147483647
Size of the DelayQueue: 1
DelayQueue Remaining Capacity:2147483647
Size of the DelayQueue: 0
DelayQueue Remaining Capacity:2147483647
```