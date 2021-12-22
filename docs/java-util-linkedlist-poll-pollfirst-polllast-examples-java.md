# Java.util.LinkedList.poll()、pollFirst()、pollLast()用 Java 举例

> 原文:[https://www . geesforgeks . org/Java-util-linked list-poll first-poll last-examples-Java/](https://www.geeksforgeeks.org/java-util-linkedlist-poll-pollfirst-polllast-examples-java/)

Java 的链表类提供了一个函数，允许一个名为 poll()的基于“**队列的**”工作。这个函数不仅返回删除第一个元素，而且**还在删除时显示**，因此在日常生活问题和竞争性编程中也有很多用法。poll()有 **3** 种变体，本文将讨论这三种变体。
**1。poll()** :此方法**检索**，**移除此列表的**头(第一个元素)**。**

```java
Declaration : 
   public E poll()
Return Value : 
      This method returns the first element of this list, or null if this list is empty.

```

```java
// Java code to demonstrate the working
// of poll() in linked list
import java.util.*;
public class LinkedListPoll {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial Linked List is : " + list);

        // using poll() to retrieve and remove the head
        // removes and displays "Geeks"
        System.out.println("Head element of the list is : " + list.poll());

        // printing the resultant list
        System.out.println("Linked List after removal using poll() : " + list);
    }
}
```

输出:

```java
The initial Linked List is : [Geeks, 4, Geeks, 8]
Head element of the list is : Geeks
Linked List after removal using poll() : [4, Geeks, 8]

```

**2。pollsfirst():**此方法**检索**，**删除此列表的****第一个元素**，如果此列表为空，则返回 null。

```java
Declaration : 
  public E pollFirst()
Return Value : 
   This method returns the first element of this list, or null if this list is empty

```

```java
// Java code to demonstrate the working
// of pollFirst() in linked list
import java.util.*;
public class LinkedListPollFirst {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial Linked List is : " + list);

        // using pollFirst() to retrieve and remove the head
        // removes and displays "Geeks"
        System.out.println("Head element of the list is : " + list.pollFirst());

        // printing the resultant list
        System.out.println("Linked List after removal using pollFirst() : " + list);
    }
}
```

输出:

```java
The initial Linked List is : [Geeks, 4, Geeks, 8]
Head element of the list is : Geeks
Linked List after removal using pollFirst() : [4, Geeks, 8]

```

**3。pollLast() :** 此方法**检索**，**删除此列表的****最后一个元素**，如果此列表为空，则返回 null。

```java
Declaration : 
  public E pollLast()
Return Value : 
   This method returns the last element of this list, or null if this list is empty.

```

```java
// Java code to demonstrate the working
// of pollLast() in linked list
import java.util.*;
public class LinkedListPollLast {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial Linked List is : " + list);

        // using pollLast() to retrieve and remove the tail
        // removes and displays 8
        System.out.println("Tail element of the list is : " + list.pollLast());

        // printing the resultant list
        System.out.println("Linked List after removal using pollLast() : " + list);
    }
}
```

输出:

```java
The initial Linked List is : [Geeks, 4, Geeks, 8]
Tail element of the list is : 8
Linked List after removal using pollLast() : [Geeks, 4, Geeks]

```

**实际应用:**该功能在“**队列管理**系统以及可以想到的“第一次淘汰”游戏中有潜在用途。下面讨论前一个例子。

```java
// Java code to demonstrate the practical
// application of poll() in linked list
import java.util.*;
public class LinkedListPollApp {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding queue entry of people
        // in order
        list.add("Astha");
        list.add("Shambhavi");
        list.add("Nikhil");
        list.add("Manjeet");

        // printing the list
        System.out.println("The initial queue is : " + list);

        System.out.print("The order of exit is : ");

        while (!list.isEmpty()) {
            // using poll() to display the order of exit from queue
            System.out.print(list.poll() + " <-- ");
        }
    }
}
```

输出:

```java
The initial queue is : [Astha, Shambhavi, Nikhil, Manjeet]
The order of exit is : Astha <-- Shambhavi <-- Nikhil <-- Manjeet <-- 

```

本文由 [**阿斯特哈·泰亚吉**](https://auth.geeksforgeeks.org/profile.php?user=Astha Tyagi&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。