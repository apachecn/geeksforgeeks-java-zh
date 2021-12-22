# Java 中的 ConcurrentSkipListSet clear()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-clear-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-clear-method-in-java/)

**java . util . concurrentSkiplistset . clear()**方法是 Java 中的一个内置函数，它从这个集合中移除所有元素。

**语法:**

```java
 ConcurrentSkipListSet.clear()

```

**参数:**函数不接受任何参数。

**返回值:**函数不返回任何内容。

下面的程序说明了 ConcurrentSkipListSet.clear()方法:

**程序 1:**

```java
/* Java Program Demonstrate clear()
method of ConcurrentSkipListSet() */
import java.util.concurrent.*;
class ConcurrentSkipListSetClearExample1 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<Integer> Lset = 
                   new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            Lset.add(i);

        // Printing elements of the set
        System.out.println("The set contains: " + Lset);

        // Clear the set
        Lset.clear();

        // Printing elements of the set after clear operation
        System.out.println("After clear operation the set contains: " 
                                                             + Lset);
    }
}
```

**输出:**

```java
The set contains: [10, 20, 30, 40, 50]
After clear operation the set contains: []

```

**程序二:**

```java
/* Java Program Demonstrate clear()
method of ConcurrentSkipListSet() */
import java.util.concurrent.*;
class ConcurrentSkipListSetClearExample2 {
    public static void main(String[] args)
    {
        // Creating a set object
        ConcurrentSkipListSet<String> Lset = 
                    new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        Lset.add("alex");
        Lset.add("bob");
        Lset.add("chuck");
        Lset.add("drake");
        Lset.add("eric");

        // Printing elements of the set
        System.out.println("The set contains: " + Lset);

        // Clear the set
        Lset.clear();

        // Printing elements of the set after clear operation
        System.out.println("After clear operation the set contains: " 
                                                              + Lset);
    }
}
```

**输出:**

```java
The set contains: [alex, bob, chuck, drake, eric]
After clear operation the set contains: []

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#clear--)