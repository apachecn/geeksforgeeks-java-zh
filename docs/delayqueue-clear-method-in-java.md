# Java 中的 DelayQueue clear()方法

> 原文:[https://www . geesforgeks . org/delay queue-clear-method-in-Java/](https://www.geeksforgeeks.org/delayqueue-clear-method-in-java/)

Java 中 DelayQueue 的 **clear()** 方法用于移除当前 DelayQueue 对象中的所有元素。该调用返回后，队列将为空。队列中延迟没有到期的元素会自动从队列中丢弃。

**语法**:

```
public void clear()
```

**参数:**该方法不取任何参数。

**返回值:**此方法不返回值。

下面的程序说明了上面的方法:

```
// Java program to illustrate the clear() method
// of DelayQueue class

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create a DelayQueue instance
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Create an Object of type Delayed
        Delayed obj = new Delayed() {
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

        // Add the obj to the queue
        queue.add(obj);

        // Check if queue is empty
        System.out.println("Is queue empty() : "
                           + queue.isEmpty());

        // Remove all elements from queue
        // uing clear() method
        queue.clear();

        // Check if queue is empty
        System.out.println("Is queue empty after calling clear() : "
                           + queue.isEmpty());
    }
}
```

**Output:**

```
Is queue empty() : false
Is queue empty after calling clear() : true

```