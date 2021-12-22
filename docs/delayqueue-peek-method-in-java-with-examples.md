# Java 中的 DelayQueue peek()方法，带示例

> 原文:[https://www . geeksforgeeks . org/delay queue-peek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-peek-method-in-java-with-examples/)

[**DelayQueue**](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/) 的 **peek()** 方法用于检索 DelayQueue 的头，但不会将其移除，就像 poll()方法中头从 DelayQueue 中移除一样。

**语法:**

```java
public E peek ()
```

**参数:**
此方法不接受任何参数。

**返回:**
这个方法返回延迟队列的头，并且不从这个延迟队列中删除它。

**异常:**
**空指针异常:**如果头部不存在，该函数将返回空。

下面用 Java 编程来说明 DelayQueue peek():

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate DelayQueue peek() method

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
        // peek() method for returning head of the DelayQueue

        System.out.println("Head of the DelayQueue: "
                           + DQ.peek());
        // print DelayQueue
        System.out.println("\nAfter peek() method, DelayQueue: "
                           + DQ);
    }
}
```

**Output:** 

```java
Original DelayQueue: [
{ A, time=1545817334485}, 
{ B, time=1545817334486}, 
{ C, time=1545817334487}, 
{ D, time=1545817334488}]

Head of the DelayQueue: 
{ A, time=1545817334485}

After peek() method, DelayQueue: [
{ A, time=1545817334485}, 
{ B, time=1545817334486}, 
{ C, time=1545817334487}, 
{ D, time=1545817334488}]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate DelayQueue peek() method

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
        // removing all elements
        DQ.clear();
        // peek() method for returning head of the DelayQueue
        System.out.println("Head of the DelayQueue: " + DQ.peek());
    }
}
```

**Output:** 

```java
Original DelayQueue: [
{ A, time=1545817342666}, 
{ B, time=1545817342667}]

Head of the DelayQueue: null
```