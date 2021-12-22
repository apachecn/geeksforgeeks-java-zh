# Java 中的 DelayQueue drainTo()方法，示例

> 原文:[https://www . geeksforgeeks . org/delay queue-drain to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-drainto-method-in-java-with-examples/)

[延迟队列](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/)的**drain to(Collection<E>c)**方法从该延迟队列中移除所有可用元素，并将它们添加到作为参数传递的给定集合中。这种方法比重复轮询这个延迟队列更有效。
也有失败的可能。如果延迟队列试图将队列排到自身，将导致 IllegalArgumentException。此外，如果在操作过程中修改了指定的集合，则此操作的行为是未定义的。
**语法:**

```
public int drainTo (Collection<E> c)
```

**参数:**该方法接受一个参数 c，该参数表示从延迟队列传输元素的集合。
**返回值:**该函数返回转移的元素数量。
**异常:**此方法抛出以下异常:

*   **取消支持操作异常**–如果集合无法添加元素。
*   **class castexception**–如果元素的类停止了向集合中添加元素的方法。
*   **NullPointRexception**–如果集合为空。
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中。

下面的程序说明了 DelayQueue.drainTo()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate DelayQueue drainTo() method

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

        System.out.println("Before drainTo():");
        System.out.println("DelayQueue: " + DQ);

        // create a ArrayList to pass as parameter to drainTo()
        ArrayList<DelayObject> array
            = new ArrayList<DelayObject>();

        // Apply drainTo method and pass array as parameter
        int response = DQ.drainTo(array);
        // print no of element passed
        System.out.println("\nNo of element passed: "
                           + response);

        // printing Arraylist and deque
        // after applying drainTo() method
        System.out.println("\nAfter drainTo():");
        System.out.println("DelayQueue : \n"
                           + DQ);
        System.out.println("ArrayList : \n"
                           + array);
    }
}
```

**Output:** 

```
Before drainTo():
DelayQueue: [
{ A, time=1546842375114}, 
{ B, time=1546842375115}, 
{ C, time=1546842375116}, 
{ D, time=1546842375117}]

No of element passed: 4

After drainTo():
DelayQueue : 
[]
ArrayList : 
[
{ A, time=1546842375114}, 
{ B, time=1546842375115}, 
{ C, time=1546842375116}, 
{ D, time=1546842375117}]
```