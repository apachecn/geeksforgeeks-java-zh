# Java 中的 LinkedTransferQueue peek()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-peek-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-peek-method-in-java/)

**java . util . concurrent . linkedtransferqueue . peek()**方法是 Java 中的内置函数，用于在队列非空的情况下返回队列头。

**语法:**

```
LinkedTransferQueue.peek()  

```

**参数:**函数不接受任何参数。

**返回值:**如果队列非空，函数返回队列头，否则返回 null。

下面的程序说明了 LinkedTransferQueue.peek()方法:

**程序 1:**

```
// Java Program Demonstrate peek()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueuePeekExample1 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Character> queue = 
                      new LinkedTransferQueue<Character>();

        // Adding elements to this queue
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            queue.add(ch);
        }

        // Printing the head of the queue
        System.out.println("The head of the queue is " 
                                        + queue.peek());

        // Printing all the elements of the queue
        System.out.println("The elements in the queue :");
        for (Character i : queue)
            System.out.print(i + " ");
    }
}
```

**输出:**

```
The head of the queue is A
The elements in the queue :
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

```

**程序二:**

```
// Java Program Demonstrate peek()
// method of LinkedTransferQueue 

import java.util.concurrent.LinkedTransferQueue;

class LinkedTransferQueuePeekExample2 {
    public static void main(String[] args)
    {
        // Initializing the queue
        LinkedTransferQueue<Integer> queue = 
                 new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 50; i += 10)
            queue.add(i);

        // Printing the head of the queue
        System.out.println("The head of the queue is " 
                                           + queue.peek());

        // Printing all the elements of the queue
        System.out.println("The elements in the queue :");
        for (Integer i : queue)
            System.out.print(i + " ");
    }
}
```

**输出:**

```
The head of the queue is 10
The elements in the queue :
10 20 30 40 50

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # peek()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#peek())