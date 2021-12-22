# Java 中的抽象队列 addAll()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract queue-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-addall-method-in-java-with-examples/)

**[【抽象队列】](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)** 的 **addAll(E e)** 方法将指定集合中的所有元素添加到该队列中。

**语法:**

```java
public boolean addAll(Collection c)
```

**参数:**该方法接受一个强制参数**集合**，该集合包含要添加到该队列的元素

**返回:**如果该队列由于调用而改变，则该方法返回**真**

**异常:**此方法抛出以下异常:

*   **[illegalstateexception]** : If due to insertion restriction
*   **Nullpointerexception** if all elements cannot be added at this time: if the specified collection contains null elements and this queue does not allow null elements, or if the specified collection is empty.
*   **classcastexception** –If the class of an element of the specified collection prevents it from being added to this queue.
*   **illegalargumentexception** –If some attributes of an element of the specified set prevent it from being added to this queue, or if the specified set is this queue.

下面的程序说明了 addAll()方法:

**程序 1:**

```java
// Java program to illustrate the
// AbstractQueue addAll() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer>
            AQ1 = new LinkedBlockingQueue<Integer>();

        // Populating AQ1
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print AQ
        System.out.println("AbstractQueue1 contains : " + AQ1);

        AbstractQueue<Integer>
            AQ2 = new LinkedBlockingQueue<Integer>();

        // print AQ2 initially
        System.out.println("AbstractQueue2 initially contains : " + AQ2);

        // adds elements of AQ1 in AQ2
        AQ2.addAll(AQ1);

        System.out.println("AbstractQueue1 after addition contains : " + AQ2);
    }
}
```

**输出:**

```java
AbstractQueue1 contains : [10, 20, 30, 40, 50]
AbstractQueue2 initially contains : []
AbstractQueue1 after addition contains : [10, 20, 30, 40, 50]

```

**程序 2:** 程序为*非法状态异常*

```java
// Java program to illustrate the
// AbstractQueue addAll() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ1 = new LinkedBlockingQueue<Integer>();

            // Populating AQ1
            AQ1.add(10);
            AQ1.add(20);
            AQ1.add(30);
            AQ1.add(40);
            AQ1.add(50);

            // print AQ
            System.out.println("AbstractQueue1 contains : " + AQ1);

            AbstractQueue<Integer>
                AQ2 = new LinkedBlockingQueue<Integer>(3);

            // print AQ2 initially
            System.out.println("AbstractQueue2 initially contains : " + AQ2);

            // adds elements of AQ1 in AQ2
            AQ2.addAll(AQ1);

            System.out.println("AbstractQueue1 after addition contains : " + AQ2);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
AbstractQueue1 contains : [10, 20, 30, 40, 50]
AbstractQueue2 initially contains : []
Exception: java.lang.IllegalStateException: Queue full

```

**程序 3:** 程序为*空指针异常*

```java
// Java program to illustrate the
// AbstractQueue addAll() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ1 = null;

            // print AQ
            System.out.println("AbstractQueue1 contains : " + AQ1);

            AbstractQueue<Integer>
                AQ2 = new LinkedBlockingQueue<Integer>(3);

            // print AQ2 initially
            System.out.println("AbstractQueue2 initially contains : " + AQ2);

            // adds elements of AQ1 in AQ2
            AQ2.addAll(AQ1);

            System.out.println("AbstractQueue1 after addition contains : " + AQ2);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
AbstractQueue1 contains : null
AbstractQueue2 initially contains : []
Exception: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/abstractqueue . html # addAll-E-](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#addAll-E-)