# Java 中的 concurrentlinkedequespliterator()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-spliterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-spliterator-method-in-java-with-examples/)

**concurrentlinkedeque**的 **spliterator()** 方法返回一个 concurrentlinkedeque 元素上的 spliterator。返回的迭代器弱一致。在 Java 8 中，拆分器可以与 Streams 一起使用。分割器也可以单独和批量遍历元素。

**语法:**

```
public Spliterator spliterator()
```

**返回:**该方法在 ConcurrentLinkedDeque 中的元素上返回一个**拆分器**。

下面的程序说明了 ConcurrentLinkedDeque 的 spliterator()方法:

**程序 1:**

```
// Java Program to demonstrate spliterator()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CBD
            = new ConcurrentLinkedDeque<Integer>();

        // Add elements
        CBD.add(22);
        CBD.add(34);
        CBD.add(45);
        CBD.add(67);

        // create Spliterator of Deque
        // using spliterator() method
        Spliterator<Integer> numbers
            = CBD.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Numbers:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining(
            (n) -> System.out.println(n));
    }
}
```

**Output:**

```
Size of Spliterator : 9223372036854775807
list of Numbers:
22
34
45
67

```

**程序 2:**

```
// Java Program to demonstrate spliterator()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CBD
            = new ConcurrentLinkedDeque<String>();

        // Add numbers to front of ConcurrentLinkedDeque
        CBD.add("Geeks");
        CBD.add("forGeeks");
        CBD.add("A");
        CBD.add("Computer");
        CBD.add("Portal");

        // create Spliterator of Deque
        // using spliterator() method
        Spliterator<String> numbers
            = CBD.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Strings:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining(
            (n) -> System.out.println(n));
    }
}
```

**Output:**

```
Size of Spliterator : 9223372036854775807
list of Strings:
Geeks
forGeeks
A
Computer
Portal

```