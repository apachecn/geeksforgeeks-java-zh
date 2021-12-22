# Java 中的 LinkedTransferQueue spliterator()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-spliterator-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-spliterator-method-in-java/)

**java . util . concurrent . linkedtransferqueue . spliterator()**方法是 Java 中的一个内置函数，它在这个队列的元素之间返回一个弱一致的 Spliterator。

**语法:**

```
LinkedTransferQueue.spliterator()  

```

**参数:**函数不接受任何参数。

**返回值:**该函数返回一个跨该队列元素的拆分器。

下面的程序说明了 LinkedTransferqueue . spliterator()方法:

**程序 1:**

```
// Java Program Demonstrate Spliterator()
// method of LinkedTransferQueue 

import java.util.Spliterator;
import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueSpliteratorExample1 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<String> queue = 
                   new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.add("Gfg");
        queue.add("is");
        queue.add("best!!");

        // spliterator split and iterate
        // the split parts in parallel
        Spliterator<String> str = queue.spliterator();

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

**Output:**

```
Lower case = Gfg
 Upper case = GFG

 Lower case = is
 Upper case = IS

 Lower case = best!!
 Upper case = BEST!!

```

**程序 2:**

```
// Java Program Demonstrate Spliterator()
// method of LinkedTransferQueue 

import java.util.Spliterator;
import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueSpliteratorExample2 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Character> queue =
                  new LinkedTransferQueue<Character>();

        // Adding elements to this queue
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            queue.add(ch);
        }

        // Printing elements in the queue
        System.out.print("The elements in the queue are : ");

        // spliterator  split and iterate
        // the split parts in parallel
        Spliterator<Character> str = queue.spliterator();

        // if element exists tryAdvance() will perform action
        while (str.tryAdvance((n) -> System.out.print(n + " ")))
            ;
    }
}
```

**Output:**

```
The elements in the queue are : A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

```