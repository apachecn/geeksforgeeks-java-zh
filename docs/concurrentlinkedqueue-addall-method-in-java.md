# Java 中的 ConcurrentLinkedQueue addAll()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-addall-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-addall-method-in-java/)

**ConcurrentLinkedQueue** 的 **addAll()** 方法用于在 ConcurrentLinkedQueue 的末尾插入集合的所有元素，作为参数传递给该方法。元素的插入顺序与集合迭代器返回的顺序相同。

**语法:**

```java
public boolean addAll(Collection<? extends E> c)
```

**参数:**这个方法取一个参数 **c** ，这个参数代表一个集合，这个集合的元素需要被追加到这个 ConcurrentLinkedQueue 的末尾。

**返回:**如果至少执行了一个插入动作，该方法返回**真**。

**异常:**这个方法抛出两个不同的异常:

*   **[null pointer exception]** -If the passed set or any of its elements is null.
*   **illegalargumentexception** –If the passed collection is the queue itself.

下面的程序说明了并发链接队列的 addAll()方法:

**示例 1:** 试图向 ConcurrentLinkedQueue 添加数字列表。

```java
// Java Program Demonstrate addAll()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add Numbers to queue
        queue.add(4353);

        // create a ArrayList of Numbers
        ArrayList<Integer> arraylist = new ArrayList<Integer>();

        // add some numbers to ArrayList
        arraylist.add(377139);
        arraylist.add(624378);
        arraylist.add(654793);
        arraylist.add(764764);
        arraylist.add(838494);
        arraylist.add(632845);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // Displaying the existing Collection
        System.out.println("Collection to be added: " + arraylist);

        // apply addAll() method and passed the arraylist as parameter
        boolean response = queue.addAll(arraylist);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Collection added: " + response);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [4353]
Collection to be added: [377139, 624378, 654793, 764764, 838494, 632845]
Collection added: true
ConcurrentLinkedQueue: [4353, 377139, 624378, 654793, 764764, 838494, 632845]

```

**示例 2:** 试图向 ConcurrentLinkedQueue 添加字符串列表。

```java
// Java Program Demonstrate addAll()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Aman");
        queue.add("Amar");

        // create a ArrayList of Numbers
        ArrayList<String> arraylist = new ArrayList<String>();

        // add some numbers to ArrayList

        arraylist.add("Sanjeet");
        arraylist.add("Rabi");
        arraylist.add("Debasis");
        arraylist.add("Raunak");
        arraylist.add("Mahesh");

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // Displaying the existing Collection
        System.out.println("Collection to be added: " + arraylist);

        // apply addAll() method and passed the arraylist as parameter
        boolean response = queue.addAll(arraylist);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Collection added: " + response);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [Aman, Amar]
Collection to be added: [Sanjeet, Rabi, Debasis, Raunak, Mahesh]
Collection added: true
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi, Debasis, Raunak, Mahesh]

```

**示例 3:** 显示**空指针异常**

```java
// Java Program Demonstrate addAll()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Aman");
        queue.add("Amar");

        // create a ArrayList which is equal to null
        ArrayList<String> arraylist = null;

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // Displaying the existing Collection
        System.out.println("Collection to be added: " + arraylist);

        try {
            // apply addAll() method and pass the arraylist as parameter
            // since the arraylist is null, exception will be thrown
            boolean response = queue.addAll(arraylist);
        }
        catch (NullPointerException e) {
            System.out.println("Exception thrown while adding null: " + e);
        }
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [Aman, Amar]
Collection to be added: null
Exception thrown while adding null: java.lang.NullPointerException

```

**示例 4:** 显示 IllegalArgumentException

```java
// Java Program Demonstrate addAll()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Aman");
        queue.add("Amar");

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        try {
            // apply addAll() method and passed the queue as parameter
            boolean response = queue.addAll(queue);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown while adding queue"
                               + " to itself when collection is required: " + e);
        }
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [Aman, Amar]
Exception thrown 
 while adding queue to itself
 when collection is required: java.lang.IllegalArgumentException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # addAll-Java . util . collection-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#addAll-java.util.Collection-)