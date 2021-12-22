# Java 中的 concurrentlinkedequepoll()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-poll-method-in-Java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-poll-method-in-java-with-example/)

**的 **poll()** 方法 concurrentlinkedeque**返回 Deque 容器中的 front 元素并删除它。如果容器是空的，它将返回**空值**。

**语法:**

```
public E poll()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不是空的，这个方法返回*前元素*并删除它。如果容器是空的，它将返回*空值*。

以下程序说明了并发链接请求的轮询()方法:

**程序 1:**

```
// Java Program Demonstrate poll()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD.add(7855642);
        CLD.add(35658786);
        CLD.add(5278367);
        CLD.add(74381793);

        // Print the queue
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);

        System.out.println("Front element in Deque: "
                           + CLD.poll());

        // One element is deleted as poll was called
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: 7855642
ConcurrentLinkedDeque: [35658786, 5278367, 74381793]

```

**程序 2:**

```
// Java Program Demonstrate poll()
// method of ConcurrentLinkedDeque
// when Deque is empty

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD.add(7855642);
        CLD.add(35658786);
        CLD.add(5278367);
        CLD.add(74381793);

        // Print the queue
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);

        // empty deque
        CLD.clear();

        System.out.println("Front element in Deque: "
                           + CLD.poll());
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```