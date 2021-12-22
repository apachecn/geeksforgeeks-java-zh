# Java 中的 DelayQueue poll()方法，示例

> 原文:[https://www . geesforgeks . org/delay queue-poll-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-poll-method-in-java-with-examples/)

[**延迟队列**](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/) 的**轮询()**方法用于检索延迟队列的头部。该方法还从延迟队列中移除头部。因此，当调用轮询方法时，延迟队列的大小减少一。
**语法:**

```
public E poll ()
```

**参数:**
此方法不接受任何参数。
**返回:**
该方法返回延迟队列的头部，并将其从该延迟队列中移除。
**异常:**
**空指针异常:**如果磁头不存在，此功能将返回空。
下面程序来举例说明 Java 中的 DelayQueue poll():
**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue poll() method

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

        // Print delayqueue
        System.out.println("Original DelayQueue: "
                           + DQ + "\n");
        // Print size of original DelayQueue
        System.out.println("Original DelayQueue size: "
                           + DQ.size() + "\n");

        // poll() method for returning head of the DelayQueue
        System.out.println("Head of the DelayQueue: "
                           + DQ.poll());
        // print DelayQueue size after poll method
        System.out.println("\nAfter poll() method, DelayQueue size: "
                           + DQ.size());
    }
}
```

**Output:** 

```
Original DelayQueue: [
{ A, time=1545817370442}, 
{ B, time=1545817370443}, 
{ C, time=1545817370444}, 
{ D, time=1545817370445}]

Original DelayQueue size: 4

Head of the DelayQueue: 
{ A, time=1545817370442}

After poll() method, DelayQueue size: 3
```

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue poll() method

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

        // Print size of original DelayQueue
        System.out.println("Original DelayQueue size: "
                           + DQ.size() + "\n");

        // poll() method for returning head of the DelayQueue
        System.out.println("Head of the DelayQueue: "
                           + DQ.poll());
    }
}
```

**Output:** 

```
Original DelayQueue size: 0

Head of the DelayQueue: null
```