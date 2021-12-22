# Java 中 DelayQueue size()方法示例

> 原文:[https://www . geeksforgeeks . org/delay queue-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/delayqueue-size-method-in-java-with-examples/)

Java 中 DelayQueue 类的 **size()** 方法用于返回给定队列中存在的元素数量。如果元素数量大于整数。最大值，然后是整数。最大值作为延迟队列的大小返回。
**语法** :

```
public int size()
```

**参数:**不接受任何参数。
**返回值:**返回一个整数，即队列的长度。
下面程序举例说明 Java 中 DelayQueue 的 size()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the size() method
// of DelayQueue class

import java.util.concurrent.DelayQueue;
import java.util.concurrent.Delayed;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String args[])
    {
        // Create a DelayQueue Instance
        DelayQueue<Delayed> queue = new DelayQueue<Delayed>();

        // Create an object of type Delayed
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

        // Insert the object to this DelayQueue
        // Size of the queue after insertion will be 1
        queue.add(obj);

        // print the size of this DelayQueue using
        // size() method
        System.out.println("Size : " + queue.size());
    }
}
```

**Output:** 

```
Size : 1
```