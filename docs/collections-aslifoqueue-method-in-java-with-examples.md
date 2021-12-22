# Java 中的集合 asLifoQueue()方法，示例

> 原文:[https://www . geesforgeks . org/collections-aslifoqueue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-aslifoqueue-method-in-java-with-examples/)

类的 **asLifoQueue()** 方法用于返回一个作为后进先出(Lifo)队列的视图。方法 add 被映射到 push，remove 被映射到 pop 等等。当您想要使用需要队列的方法，但又需要后进先出排序时，这个视图会很有用。
该方法返回的队列上的每个方法调用都会导致后备队列上只有一个方法调用，只有一个例外。addAll 方法被实现为在后台数据库上的一系列 addFirst 调用。
**语法:**

```
public static Queue asLifoQueue(Deque deque)
```

**参数:**该方法以**德清**为参数，将其转换为后进先出队列。
**返回值:**该方法从 deque 返回一个 **LifoQueue** 。
以下是举例说明 *asLifoQueue()* 方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asLifoQueue() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // creating object of Deque<Integer>
            Deque<Integer> deque = new ArrayDeque<Integer>(7);

            // Adding element to deque
            deque.add(1);
            deque.add(2);
            deque.add(3);
            deque.add(4);
            deque.add(5);

            // get queue from the deque
            // using asLifoQueue() method
            Queue<Integer> nq = Collections.asLifoQueue(deque);

            // printing the Queue
            System.out.println("View of the queue is: " + nq);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
View of the queue is: [1, 2, 3, 4, 5]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asLifoQueue() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of Deque<Integer>
            Deque<String> deque = new ArrayDeque<String>(7);

            // Adding element to deque
            deque.add("Ram");
            deque.add("Gopal");
            deque.add("Verma");

            // get queue from the deque
            // using asLifoQueue() method
            Queue<String> nq = Collections.asLifoQueue(deque);

            // printing the Queue
            System.out.println("View of the queue is: " + nq);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
View of the queue is: [Ram, Gopal, Verma]
```