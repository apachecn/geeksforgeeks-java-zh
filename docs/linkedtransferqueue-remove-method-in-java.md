# Java 中的 LinkedTransferQueue remove()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-remove-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-remove-method-in-java/)

**java . util . concurrent . linkedtransferqueue . remove()**方法是 Java 中的一个内置函数，用于在元素出现在这个队列中时将其移除。

**语法:**

```
LinkedTransferQueue.remove(Object o)
```

**参数:**该功能接受单个参数 *o* ，即要移除的对象。

**返回值:**该函数在成功移除对象时返回真布尔值，否则返回假。

下面的程序说明了 LinkedTransferQueue.remove()方法:

**程序 1:** 队列中存在要删除的元素。

```
// Java Program Demonstrate remove()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueRemoveExample1 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Integer> queue = 
              new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 1; i <= 5; i++)
            queue.add(i);

        // Printing the elements of the queue
        System.out.println("The elements in the queue are:");
        for (Integer i : queue)
            System.out.print(i + " ");

        // remove() method will remove the specified
        // element from the queue
        queue.remove(1);
        queue.remove(5);

        // Printing the elements of the queue
        System.out.println("\nRemaining elements in queue : ");
        for (Integer i : queue)
            System.out.print(i + " ");
    }
}
```

**输出:**

```
The elements in the queue are:
1 2 3 4 5 
Remaining elements in queue : 
2 3 4

```

**程序 2:** 要删除的元素不在队列中。

```
// Java Program Demonstrate remove()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueueRemoveExample2 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Integer> queue = 
                    new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 15; i++)
            queue.add(i);

        // Printing the elements of the queue
        System.out.println("The elements in the queue are:");
        for (Integer i : queue)
            System.out.print(i + " ");

        // remove() method will remove the specified
        // element from the queue
        queue.remove(1);
        queue.remove(5);

        // Printing the elements of the queue
        System.out.println("\nRemaining elements in queue : ");
        for (Integer i : queue)
            System.out.print(i + " ");
    }
}
```

**输出:**

```
The elements in the queue are:
10 11 12 13 14 15 
Remaining elements in queue : 
10 11 12 13 14 15

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # remove(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#remove(java.lang.Object))