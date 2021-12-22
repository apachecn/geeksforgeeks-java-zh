# Java 中的 ConcurrentLinkedDeque pop()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-pop-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-pop-method-in-java-with-examples/)

Java 中的**Java . util . ConcurrentLinkedDeque . pop()**方法用于从 concurrentlinkedeque 中弹出一个元素。该元素从 ConcurrentLinkedDeque 的顶部弹出，并从其中移除。
**语法:**

```java
ConcurrentLinkedDeque.pop()
```

**参数:**该方法不取任何参数。
**返回值:**这个方法返回出现在 ConcurrentLinkedDeque 顶部的元素，然后删除它。
**异常:**方法抛出*emptycon currentlinkedrequestexception*如果 ConcurrentLinkedDeque 为空则抛出。
下面的程序说明了 Java . util . concurrentlinkedrequest . pop()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate pop()

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CLD
            = new ConcurrentLinkedDeque<String>();

        // Use add() method to add elements
        CLD.push("Welcome");
        CLD.push("To");
        CLD.push("Geeks");
        CLD.push("For");
        CLD.push("Geeks");

        // Displaying the ConcurrentLinkedDeque
        System.out.println("Initial ConcurrentLinkedDeque: "
                           + CLD);

        // Removing elements using pop() method
        System.out.println("Popped element: " + CLD.pop());
        System.out.println("Popped element: " + CLD.pop());

        // Displaying the ConcurrentLinkedDeque after pop operation
        System.out.println("ConcurrentLinkedDeque after pop operation "
                           + CLD);
    }
}
```

**输出:**

```java
Initial ConcurrentLinkedDeque: [Geeks, For, Geeks, To, Welcome]
Popped element: Geeks
Popped element: For
ConcurrentLinkedDeque after pop operation [Geeks, To, Welcome]
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate pop()

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD
            = new ConcurrentLinkedDeque<Integer>();

        // Use add() method to add elements
        CLD.push(10);
        CLD.push(15);
        CLD.push(30);
        CLD.push(20);
        CLD.push(5);

        // Displaying the ConcurrentLinkedDeque
        System.out.println("Initial ConcurrentLinkedDeque: "
                           + CLD);

        // Removing elements using pop() method
        System.out.println("Popped element: " + CLD.pop());
        System.out.println("Popped element: " + CLD.pop());

        // Displaying the ConcurrentLinkedDeque after pop operation
        System.out.println("ConcurrentLinkedDeque after pop operation "
                           + CLD);
    }
}
```

**Output:** 

```java
Initial ConcurrentLinkedDeque: [5, 20, 30, 15, 10]
Popped element: 5
Popped element: 20
ConcurrentLinkedDeque after pop operation [30, 15, 10]
```