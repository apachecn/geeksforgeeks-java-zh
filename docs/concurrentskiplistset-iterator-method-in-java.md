# Java 中的 ConcurrentSkipListSet 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-iterator-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-iterator-method-in-java/)

**java . util . concurrentSkiplistset**的**迭代器()**方法是 Java 中的内置函数，用于以*升序*返回该集合中元素的迭代器。
**语法:**

```
ConcurrentSkipListSet.iterator()  
```

**返回值:**函数以升序返回该集合中元素的迭代器。

下面的程序说明了 Java . util . concurrentskiplistset . iterator():
**程序 1:**

```
// Java Program Demonstrate iterator()
// method of ConcurrentSkipListSet 

import java.util.Iterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetIteratorExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<String>
            set = new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("Gfg");
        set.add("is");
        set.add("fun!!");

        // Returns an iterator over the elements
        Iterator<String> iterator = set.iterator();

        // Printing the elements of the set
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
    }
}
```

**Output:**

```
Gfg fun!! is

```