# Java 中的 ConcurrentLinkedDeque isEmpty()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-isempty-method-in-java-with-examples/)

**T1。isEmpty()** 是 Java 中的一个内置函数，它检查 deque 是否包含元素。

**语法:**

```
public boolean isEmpty()
```

**参数:**函数不接受任何参数。

**返回:**该方法返回一个**布尔值**,说明该数据是否为空。

下面的程序说明了 concurrentlinkedrequest . isempty()方法:

**例:1**

```
// Java Program Demonstrate
// isEmpty() method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld
            = new ConcurrentLinkedDeque<String>();

        // Displaying the existing LinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Check if the queue is empty
        // using isEmpty() method
        System.out.println("Is deque empty: "
                           + cld.isEmpty());
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: []
Is deque empty: true

```

**例:2**

```
// Java Program Demonstrate
// isEmpty() method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld
            = new ConcurrentLinkedDeque<String>();

        cld.add("GFG");
        cld.add("Gfg");
        cld.add("GeeksforGeeks");
        cld.add("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Check if the queue is empty
        // using isEmpty() method
        System.out.println("Is deque empty: "
                           + cld.isEmpty());
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: [GFG, Gfg, GeeksforGeeks, Geeks]
Is deque empty: false

```