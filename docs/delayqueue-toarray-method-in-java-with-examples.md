# Java 中的 DelayQueue toArray()方法，示例

> 原文:[https://www . geeksforgeeks . org/delay queue-to array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-toarray-method-in-java-with-examples/)

[延迟队列](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/)的 **toArray()** 方法用于返回包含延迟队列中所有元素的数组。数组中没有任何特定顺序的元素。
**语法:**

```
public Object[] toArray ()
           or
public T[] toArray (T[] a)
```

**参数:**这个方法要么不接受参数，要么取一个数组**T【】**a 作为参数，如果足够大的话，这个数组就是要存储列表元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。
**返回值:**该函数返回**一个包含该列表中所有元素的数组**。
**异常:**这个方法的第一个重载没有抛出异常。但是，第二个重载抛出以下异常:

*   **arraystorexception:**如果指定数组的运行时类型不是该队列中每个元素的运行时类型的超类型。
*   **NullPointRexception:**如果指定的数组为空。

下面的程序说明了 DelayQueue.toArray()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue toArray() method

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

        // print queue
        System.out.println("DelayQueue: "
                           + DQ);

        // Get the array of the elements
        // of the ArrayList
        // using toArray() method
        Object[] arr = DQ.toArray();

        // print the array elements
        System.out.println("Elements of DelayQueue"
                           + " as Array: "
                           + Arrays.toString(arr));
    }
}
```

**Output:** 

```
DelayQueue: [
{ A, time=1546842694862}, 
{ B, time=1546842694863}, 
{ C, time=1546842694864}, 
{ D, time=1546842694865}]
Elements of DelayQueue as Array: [
{ A, time=1546842694862}, 
{ B, time=1546842694863}, 
{ C, time=1546842694864}, 
{ D, time=1546842694865}]
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue toArray() method

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

        // print queue
        System.out.println("DelayQueue: "
                           + DQ);

        // Get the array of the elements
        // of the DelayQueue
        // using toArray(T[]) method
        Delayed arr[] = new Delayed[DQ.size()];
        arr = DQ.toArray(arr);

        // print the array elements
        System.out.println("Elements of ArrayList"
                           + " as Array: "
                           + Arrays.toString(arr));
    }
}
```

**Output:** 

```
DelayQueue: [
{ A, time=1546842699503}, 
{ B, time=1546842699504}, 
{ C, time=1546842699505}, 
{ D, time=1546842699506}]
Elements of ArrayList as Array: [
{ A, time=1546842699503}, 
{ B, time=1546842699504}, 
{ C, time=1546842699505}, 
{ D, time=1546842699506}]
```