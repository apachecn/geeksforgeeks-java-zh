# 实现并发链接请求应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-concurrentlinkedeque-API/](https://www.geeksforgeeks.org/java-program-to-implement-concurrentlinkeddeque-api/)

Java 中的[concurrentlinkedeque](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/)类是一个无界的并发 deque，它将其元素存储为链接节点，其中每个节点包含前一个和下一个节点的地址。属于 **java.util.concurrent** 包。这个类是 Java 集合框架的成员。它还扩展了对象和抽象集合类。

并发链接请求应用编程接口的特性

*   它不允许空元素。
*   迭代器弱一致。
*   并发插入、移除和访问操作跨多个线程安全执行，因此是线程安全的。
*   大小方法不是一个恒定时间的操作

实现接口

```java
1\. Serializable 
2\. Iterable<E>
3\. Collection<E>
4\. Deque<E>
5\. Queue<E>
```

**参数:** E —集合中元素的类型

**语法:**

```java
public class ConcurrentLinkedDeque<E> 
extends AbstractCollection<E>
implements Deque<E>, Serializable
```

**施工人员:**

1.  public ConcurrentLinkedDeque():它创建一个空的 deque。
2.  public ConcurrentLinkedDeque(集合 <e>c):它创建一个包含集合<e>元素的 Deque。</e></e>

**方法:**

<figure class="table">

| 方法 | 类型 | 描述 |
| --- | --- | --- |
| 添加(英、法) | 布尔 | 在文件尾部插入一个元素 |
| addAll(集合〔t0〕c) | 布尔 | 插入指定集合中的所有元素 |
| addFirst(消歧义) | 空的 | 在背景的前面添加一个元素 |
| addLast(和 e) | 空的 | 在 deque 的最后添加一个元素 |
| 清除() | 空的 | 从列表中移除所有元素 |
| 包含(对象 o) | 布尔 | 如果目标包含对象 0，则返回真 |
| 下降畸胎() | 迭代器 | 以相反的顺序返回 deque 中元素的迭代器。 |
| 元素() | E | 取回了德格的头，但没有拿走 |
| getFirst() | E | 检索数据的第一个元素 |
| getLast（） | E | 检索数据的最后一个元素 |
| isEmpty() | 布尔 | 如果目标不包含任何元素，则返回 true |
| 迭代器() | 迭代器 | 返回 deque 中元素的迭代器 |
| peek() | E | 取回了德格的头，但没有拿走 |
| 民意测验() | E | 检索并删除标题 |
| 推动 | 空的 | 将元素推送到由 deque 表示的堆栈上 |
| 流行音乐() | E | 从由 deque 表示的堆栈中弹出一个元素。 |
| 移除() | E | 检索并删除队列的头 |
| 大小() | （同 Internationalorganizations）国际组织 | 返回目标的大小 |
| toarray() | 对象[] | 返回包含所有元素的数组 |

</figure>

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement ConcurrentLinkedDeque API

// Importing all classes from
// java.util package
import java.util.*;
import java.util.concurrent.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Object 1
        // Create a ConcurrentLinkedDeque object
        // Declaring object of Integer type
        ConcurrentLinkedDeque<Integer> dq
            = new ConcurrentLinkedDeque<Integer>();

        // Adding element to the front
        // using addFirst() method
        // Custom entry
        dq.add(89);

        // Adding an element in the last
        // using addLast() method
        // Custom entry
        dq.addLast(18);

        // Adding an element to the front
        // Custom inputs
        dq.addFirst(10);
        dq.add(45);

        // Displaying the current ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque1 : "
                           + dq);

        // Object 2
        // Creating a ConcurrentLinkedDeque object
        // using ConcurrentLinkedDeque(Collection c)
        // Declaring object of Integer type
        ConcurrentLinkedDeque<Integer> ldq
            = new ConcurrentLinkedDeque<Integer>(dq);

        // Displaying the current ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque2 : "
                           + ldq);

        // Print the size of the deque
        // using size() method
        System.out.println("Size: " + ldq.size());

        // Removing all the elements from the deque
        // using clear() method
        ldq.clear();

        // Checking whether the ConcurrentLinkedDeque object
        // is empty or not
        System.out.println("Is Deque empty: "
                           + ldq.isEmpty());

        // Removing the head of deque of object1
        dq.remove();

        // Iterating over elements and
        // printing deque of object1
        Iterator it = dq.iterator();

        // Condition check using hasNext() which hold
        // true till single element remaining in List
        while (it.hasNext())

            // Print all the elements
            System.out.print(it.next() + " ");
    }
}
```

**Output**

```java
ConcurrentLinkedDeque1: [10, 89, 18, 45]
ConcurrentLinkedDeque2: [10, 89, 18, 45]
Size: 4
Is Deque empty: true
89 18 45 
```