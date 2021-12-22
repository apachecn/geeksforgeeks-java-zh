# 实现 ArrayDeque API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-arraydeque-api/](https://www.geeksforgeeks.org/java-program-to-implement-arraydeque-api/)

Java 中的 [ArrayDeque](https://www.geeksforgeeks.org/arraydeque-in-java/) 除了提供[德客界面](https://www.geeksforgeeks.org/deque-interface-java-example/)的实现外，还提供了如何使用可调整大小的数组。也称为阵列[双端队列](https://www.geeksforgeeks.org/deque-set-1-introduction-applications/)或阵列甲板。这是一个特殊的数组，它不断增长，允许用户在队列的每一端添加或删除一个组件。

```java
java.lang.Object

    java.util.AbstractCollection<E>

        java.util.ArrayDeque<E>
```

层次结构中 ArrayDeque 的所有**实现接口**为:

*   可序列化，
*   可克隆，
*   可重复<e>，</e>
*   收藏
*   deqo〔t0〕
*   队列〔t0〕

数组 deques 没有任何容量限制；它们按需增长以支持使用。它们不是线程安全的；在没有外部同步的情况下，它们不支持多线程并发访问。禁止使用空元素。当用作堆栈时，这个类可能比堆栈快，当用作队列时，它可能比链接列表快。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate implementation
// of ArrayDeque

import java.util.*;
public class ArrayDequeExample {
    public static void main(String[] args)
    {
        // Initializing an deque
        Deque<Integer> de_que = new ArrayDeque<Integer>(10);

        // add() method to insert
        de_que.add(10);
        de_que.add(20);
        de_que.add(30);
        de_que.add(40);
        de_que.add(50);

        for (Integer element : de_que) {
            System.out.println("Element : " + element);
        }

        System.out.println("Using clear() ");

        // clear() method
        de_que.clear();

        // addFirst() method to insert at start
        de_que.addFirst(564);
        de_que.addFirst(291);

        // addLast() method to insert at end
        de_que.addLast(24);
        de_que.addLast(14);

        System.out.println(
            "Above elements have been cleared");

        // Iterator() :
        System.out.println(
            "Elements of deque using Iterator :");

        for (Iterator itr = de_que.iterator();
             itr.hasNext();) {
            System.out.println(itr.next());
        }

        // descendingIterator() : to reverse the deque order
        System.out.println(
            "Print elements in reverse order :");

        for (Iterator dItr = de_que.descendingIterator();
             dItr.hasNext();)
        {
            System.out.println(dItr.next());
        }

        // element() method : to get Head element
        System.out.println(
            "\nHead Element using element(): "
            + de_que.element());

        // getFirst() method : to get Head element
        System.out.println(
            "Getting Head Element using getFirst(): "
            + de_que.getFirst());

        // getLast() method : to get last element
        System.out.println(
            "Getting Last Element using getLast(): "
            + de_que.getLast());

        // toArray() method :
        Object[] arr = de_que.toArray();

        System.out.println("\nArray Size : " + arr.length);

        System.out.print("Array elements : ");

        for (int i = 0; i < arr.length; i++)
            System.out.print(" " + arr[i]);

        // peek() method : to get head
        System.out.println("\nHead element : "
                           + de_que.peek());

        // poll() method : to get head
        System.out.println("Head element poll : "
                           + de_que.poll());

        // push() method :
        de_que.push(265);
        de_que.push(984);
        de_que.push(2365);

        // remove() method : to get head
        System.out.println("Head element remove : "
                           + de_que.remove());

        System.out.println("Final Array: " + de_que);
    }
}
```

**Output**

```java
Element : 10
Element : 20
Element : 30
Element : 40
Element : 50
Using clear() 
Above elements have been cleared
Elements of deque using Iterator :
291
564
24
14
Print elements in reverse order :
14
24
564
291

Head Element using element(): 291
Getting Head Element using getFirst(): 291
Getting Last Element using getLast(): 14

Array Size : 4
Array elements :  291 564 24 14
Head element : 291
Head element poll : 291
Head element remove : 2365
Final Array: [984, 265, 564, 24, 14]

```