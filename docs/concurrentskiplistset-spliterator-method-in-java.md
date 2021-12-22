# Java 中的 ConcurrentSkipListSet spliterator()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-spliterator-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-spliterator-method-in-java/)

**java . util . concurrentSkiplistset . spliterator()**方法是 Java 中的一个内置函数，它在这个集合的元素之间返回一个弱一致的 Spliterator。

**语法:**

```
ConcurrentSkipListSet.spliterator()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回该集合元素的分割器。

下面的程序说明了 concurrentskiplistset . spliterator()方法:

**程序 1:**

```
// Java Program Demonstrate Spliterator()
// method of ConcurrentSkipListSet

import java.util.Spliterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSpliteratorExample1 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<String> set = 
                    new ConcurrentSkipListSet<String>();

        // Adding elements to this set
        set.add("Gfg");
        set.add("is");
        set.add("best!!");

        // spliterator split and iterate
        // the split parts in parallel
        Spliterator<String> str = set.spliterator();

        // performs the action for each remaining element
        str.forEachRemaining(
            (n) -> {
                String lc = n.toUpperCase();
                System.out.println(" Lower case = " + n);
                System.out.println(" Upper case = " + lc);
                System.out.println();
            });
    }
}
```

**输出:**

```
Lower case = Gfg
Upper case = GFG

Lower case = best!!
Upper case = BEST!!

Lower case = is
Upper case = IS

```

**程序二:**

```
// Java Program Demonstrate Spliterator()
// method of ConcurrentSkipListSet

import java.util.Spliterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSpliteratorExample2 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Character> set = 
                         new ConcurrentSkipListSet<Character>();

        // Adding elements to this set
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            set.add(ch);
        }

        // Printing elements in the set
        System.out.print("The elements in the set are : ");

        // spliterator  split and iterate
        // the split parts in parallel
        Spliterator<Character> str = set.spliterator();

        // if element exists tryAdvance() will perform action
        while (str.tryAdvance((n) -> System.out.print(n + " ")))
            ;
    }
}
```

**输出:**

```
The elements in the set are : A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#spliterator--)