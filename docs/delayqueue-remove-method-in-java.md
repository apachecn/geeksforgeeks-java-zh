# Java 中的 DelayQueue remove()方法

> 原文:[https://www . geesforgeks . org/delay queue-remove-method-in-Java/](https://www.geeksforgeeks.org/delayqueue-remove-method-in-java/)

Java 中 DelayQueue 类的 **remove()** 方法用于从这个 DelayQueue 中移除给定对象的单个实例，比如说 **obj** (如果它存在的话)。如果给定元素被成功移除，则返回 true，否则返回 false。

**语法**:

```java
public boolean remove(Object obj)
```

**参数:**该方法将单个对象**对象**作为要从该交易队列中移除的参数。

**返回值:**如果元素删除成功，则返回布尔值*真*，否则返回*假*。

下面的程序说明了 Java 中 DelayQueue 的 remove()方法:

```java
// Java Program to illustrate the remove method
// of DelayQueue class

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create a DelayQueue instance
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Create an object of type Delayed
        Delayed ob = new Delayed() {
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

        // Add the object to DelayQueue
        queue.add(ob);

        // Print initial size of Queue
        System.out.println("Initial Size : "
                           + queue.size());

        // Remove the object ob from
        // this DelayQueue
        queue.remove(ob);

        // Print the final size of the DelayQueue
        System.out.println("Size after removing : "
                           + queue.size());
    }
}
```

**Output:**

```java
Initial Size : 1
Size after removing : 0

```