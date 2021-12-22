# Java 中的 LinkedBlockingQueue 类

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-class-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/)

**链接锁定队列**是一个基于链接节点的*可选有界*阻塞队列。这意味着 LinkedBlockingQueue 可以是有界的，如果给定它的容量，否则 LinkedBlockingQueue 将是无界的。容量可以作为参数提供给 LinkedBlockingQueue 的构造函数。该队列对元素**先进先出**进行排序。这意味着该队列的头部是该队列中存在的元素中最老的元素。这个队列的尾部是这个队列元素的最新元素。新插入的元素总是被插入到队列的尾部，队列检索操作在队列的头部获取元素。在大多数并发应用程序中，链接队列通常比基于阵列的队列具有更高的吞吐量，但可预测性较差。

容量，如果未指定，等于**整数。最大值**。每次插入时都会动态创建链接节点，直到队列的容量没有被填满。这个类及其迭代器实现了集合和迭代器接口的所有可选方法。它是 Java 集合框架的成员。

**链接锁定队列的层次结构**

![Hierarchy of LinkedBlockingQueue](img/55c7ae286e62d10f274cbcd6ff7f8fce.png)

LinkedBlockingQueue <e>扩展[抽象队列<E>T2】并实现**可序列化**、**可迭代<E>T6】、**集合<E>T8】、****](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/#:~:text=The%20AbstractQueue%20class%20in%20Java,does%20not%20allow%20null%20elements.)****[阻塞队列<E>T10】、](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/)[队列<E>T12】接口。](https://www.geeksforgeeks.org/queue-interface-java/)****</e>

**申报:**

> 公共类**链接封锁队列<E>T1】扩展抽象队列< E >实现封锁队列< E >，可序列化**

**E**–该集合中包含的元素类型。

### LinkedBlockingQueue 的构造函数:

要构造一个 LinkedBlockingQueue，我们需要从**Java . util . concurrent . LinkedBlockingQueue**导入。这里，**容量**是链接阻塞队列的大小。

**1。LinkedBlockingQueue()** :创建一个容量为整数的 LinkedBlockingQueue。最大值。

> linkeding block queue<e>lbq =新 linkeding block queue<e>()；</e></e>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// LinkedBlockingQueue() constructor

import java.util.concurrent.LinkedBlockingQueue;

public class LinkedBlockingQueueDemo {

    public static void main(String[] args)
    {

        // create object of LinkedBlockingQueue
        // using LinkedBlockingQueue() constructor
        LinkedBlockingQueue<Integer> lbq
            = new LinkedBlockingQueue<Integer>();

        // add  numbers
        lbq.add(1);
        lbq.add(2);
        lbq.add(3);
        lbq.add(4);
        lbq.add(5);

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);
    }
}
```

**Output**

```
LinkedBlockingQueue:[1, 2, 3, 4, 5]
```

**2。LinkedBlockingQueue(int capacity)**:创建具有给定(固定)容量的 LinkedBlockingQueue。

> LinkedBlockingQueue<e>lbq = new LinkedBlockingQueue(int capacity)；</e>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// LinkedBlockingQueue(int initialCapacity) constructor

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacity = 15;

        // create object of LinkedBlockingQueue
        // using LinkedBlockingQueue(int initialCapacity)
        // constructor
        LinkedBlockingQueue<Integer> lbq
            = new LinkedBlockingQueue<Integer>(capacity);

        // add  numbers
        lbq.add(1);
        lbq.add(2);
        lbq.add(3);

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);
    }
}
```

**Output**

```
LinkedBlockingQueue:[1, 2, 3]
```

**3。链接锁定队列(集合<？扩展 E > c)** :创建一个容量为整数的 LinkedBlockingQueue。MAX_VALUE，最初包含给定集合的元素，按照集合迭代器的遍历顺序添加。

> LinkedBlockingQueue<e>lbq = new LinkedBlockingQueue(集合 extends E>c)；</e>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// LinkedBlockingQueue(Collection c) constructor

import java.util.concurrent.LinkedBlockingQueue;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a Collection
        Vector<Integer> v = new Vector<Integer>();
        v.addElement(1);
        v.addElement(2);
        v.addElement(3);
        v.addElement(4);
        v.addElement(5);

        // create object of LinkedBlockingQueue
        // using LinkedBlockingQueue(Collection c)
        // constructor
        LinkedBlockingQueue<Integer> lbq
            = new LinkedBlockingQueue<Integer>(v);

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);
    }
}
```

**Output**

```
LinkedBlockingQueue:[1, 2, 3, 4, 5]
```

### 基本操作

**1。** **添加元素**

如果队列未满，LinkedBlockingQueue 的 add(E)方法会将作为参数传递的元素插入到该 LinkedBlockingQueue 尾部的方法中。如果队列已满，则此方法将等待空间变得可用，在空间可用后，它将元素插入到 LinkedBlockingQueue 中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate adding 
// elements to the LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class AddingElementsExample {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacity = 15;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> lbq
            = new LinkedBlockingQueue<Integer>(capacity);

        // add  numbers
        lbq.add(1);
        lbq.add(2);
        lbq.add(3);

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);
    }
}
```

**Output:** 

```
LinkedBlockingQueue:[1, 2, 3]
```

**2。拆卸元件**

LinkedBlockingQueue 的 [remove(Object obj)](https://www.geeksforgeeks.org/linkedblockingqueue-remove-method-in-java/) 方法只从这个 LinkedBlockingQueue 中移除给定对象的一个实例(如果存在的话)，该实例作为参数传递。如果这个队列包含一个或多个元素 e 的实例，这个方法返回真，如果这个队列包含现在从 LinkedBlockingQueue 中删除的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate removing 
// elements from the LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class RemovingElementsExample {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacity = 15;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> lbq
            = new LinkedBlockingQueue<Integer>(capacity);

        // add  numbers
        lbq.add(1);
        lbq.add(2);
        lbq.add(3);

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);

        // remove all the elements
        lbq.clear();

        // print queue
        System.out.println("LinkedBlockingQueue:" + lbq);
    }
}
```

**Output:** 

```
LinkedBlockingQueue:[1, 2, 3]
LinkedBlockingQueue:[]
```

**3。迭代**

LinkedBlockingQueue 的[迭代器()](https://www.geeksforgeeks.org/linkedblockingqueue-iterator-method-in-java/)方法以适当的顺序返回与这个 LinkedBlockingQueue 相同元素的迭代器。从这个方法返回的元素包含了从 LinkedBlockingQueue 的**第一个(头)**到**最后一个(尾)**的所有元素。返回的迭代器弱一致。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate iterating
// over LinkedBlockingQueue 

import java.util.concurrent.LinkedBlockingQueue; 
import java.util.Iterator; 

public class IteratingExample { 

    public static void main(String[] args) 
    { 
        // define capacity of LinkedBlockingQueue 
        int capacityOfQueue = 7; 

        // create object of LinkedBlockingQueue 
        LinkedBlockingQueue<String> linkedQueue 
            = new LinkedBlockingQueue<String>(capacityOfQueue); 

        // Add element to LinkedBlockingQueue 
        linkedQueue.add("John"); 
        linkedQueue.add("Tom"); 
        linkedQueue.add("Clark"); 
        linkedQueue.add("Kat"); 

        // create Iterator of linkedQueue using iterator() method 
        Iterator<String> listOfNames = linkedQueue.iterator(); 

        // print result 
        System.out.println("list of names:"); 
        while (listOfNames.hasNext()) 
            System.out.println(listOfNames.next()); 
    } 
} 
```

**Output**

```
list of names:
John
Tom
Clark
Kat
```

**4。访问元素**

LinkedBlockingQueue 的 [peek()](https://www.geeksforgeeks.org/linkedblockingqueue-peek-method-in-java/) 方法返回 LinkedBlockingQueue 的头。它检索 LinkedBlockingQueue 头的值，但不删除它。如果 LinkedBlockingQueue 为空，则此方法返回 null。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate accessing
// elements of LinkedBlockingQueue 

import java.util.concurrent.LinkedBlockingQueue; 
public class AccessingElementsExample { 

    public static void main(String[] args) 
    { 
        // define capacity of LinkedBlockingQueue 
        int capacityOfQueue = 7; 

        // create object of LinkedBlockingQueue 
        LinkedBlockingQueue<String> linkedQueue 
            = new LinkedBlockingQueue<String>(capacityOfQueue); 

        // Add element to LinkedBlockingQueue 
        linkedQueue.add("John"); 
        linkedQueue.add("Tom"); 
        linkedQueue.add("Clark"); 
        linkedQueue.add("Kat"); 

        // find head of linkedQueue using peek() method 
        String head = linkedQueue.peek(); 

        // print result 
        System.out.println("Queue is " + linkedQueue); 

        // print head of queue 
        System.out.println("Head of Queue is " + head); 

        // removing one element 
        linkedQueue.remove(); 

        // again get head of queue 
        head = linkedQueue.peek(); 

        // print result 
        System.out.println("\nRemoving one element from Queue\n"); 
        System.out.println("Queue is " + linkedQueue); 

        // print head of queue 
        System.out.println("Head of Queue is " + head); 
    } 
} 
```

**Output**

```
Queue is [John, Tom, Clark, Kat]
Head of Queue is John

Removing one element from Queue

Queue is [Tom, Clark, Kat]
Head of Queue is Tom
```

### 链接锁定队列的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [晴()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-clear-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjAJegQIABAC&usg=AOvVaw2gxGu5EFed_yKglnVNypPF) | 自动从该队列中移除所有元素。 |
| [包含(对象 o)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-contains-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjAHegQIAhAB&usg=AOvVaw2dN6OKYLn4OT7Je5uClrDN) | 如果此队列包含指定的元素，则返回 true。 |
| [沥水图(收藏<？超 E > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-drainto-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjACegQICRAC&usg=AOvVaw2nKExEuSoKWJHfUokosBFP) | 从此队列中移除所有可用元素，并将它们添加到给定集合中。 |
| [沥水图(收藏<？超 E > c，int maxElements)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-drainto-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjACegQICRAC&usg=AOvVaw2nKExEuSoKWJHfUokosBFP) | 从该队列中最多移除给定数量的可用元素，并将它们添加到给定集合中。 |
| forEach(消费者 super E>行动) | 对 Iterable 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。 |
| [迭代器()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-iterator-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjAIegQIAxAC&usg=AOvVaw3C9TbA6e2w6ZC8x4PH-Ua_) | 以正确的顺序返回该队列中元素的迭代器。 |
| [报价(E e)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-offer-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjAFegQIBhAC&usg=AOvVaw1u41zxwbGC5rbN-1sW8Z2C) | 如果可以在不超出队列容量的情况下立即插入指定元素，则在该队列的尾部插入指定元素，成功时返回 true，如果该队列已满，则返回 false。 |
| [报价(E e，长超时，时间单位单位)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-offer-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjAFegQIBhAC&usg=AOvVaw1u41zxwbGC5rbN-1sW8Z2C) | 在这个队列的尾部插入指定的元素，必要时等待指定的等待时间，直到空间变得可用。 |
| [放(E e)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/blockingqueue-put-method-in-java-with-examples/&sa=U&ved=2ahUKEwjqy-Odjf3rAhURjeYKHVfNDH84ChAWMAR6BAgAEAI&usg=AOvVaw3clu7wt4URSAh2SZXNsibS) | 在这个队列的尾部插入指定的元素，必要时等待空间变得可用。 |
| [剩余容量()](https://www.geeksforgeeks.org/linkedblockingqueue-remainingcapacity-method-in-java/) | 返回该队列在没有阻塞的情况下(在没有内存或资源限制的情况下)可以理想地接受的附加元素的数量。 |
| [移除(物体 o)](https://www.geeksforgeeks.org/linkedblockingqueue-remove-method-in-java/#:~:text=The%20remove(Object%20obj)%20method,more%20instance%20of%20element%20e.) | 从该队列中移除指定元素的单个实例(如果存在)。 |
| 移除所有(集合> c) | 移除此集合中也包含在指定集合中的所有元素(可选操作)。 |
| 移除 If(谓词 super E>过滤器) | 移除此集合中满足给定谓词的所有元素。 |
| 零售(集合> c) | 仅保留此集合中包含在指定集合中的元素(可选操作)。 |
| [尺寸()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-size-method-in-java/&sa=U&ved=2ahUKEwjqy-Odjf3rAhURjeYKHVfNDH84ChAWMAF6BAgJEAI&usg=AOvVaw0_Iex4EJLF3r-FfpTZtmUF) | 返回此队列中的元素数量。 |
| [分流器()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-8-linkedblockingqueue-spliterator-method-with-examples/&sa=U&ved=2ahUKEwjqy-Odjf3rAhURjeYKHVfNDH84ChAWMAJ6BAgIEAI&usg=AOvVaw0x1ipSbseuEV2sdSxsYiIC) | 返回该队列中元素的拆分器。 |
| [toaarray()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-toarray-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjADegQIBxAC&usg=AOvVaw1eMI8u1lJSahq86Ebmp5U7) | 按正确的顺序返回包含该队列中所有元素的数组。 |
| [toaarray(t[]a)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/linkedblockingqueue-toarray-method-in-java/&sa=U&ved=2ahUKEwiH8670jP3rAhVDg-YKHaVyDJIQFjADegQIBxAC&usg=AOvVaw1eMI8u1lJSahq86Ebmp5U7) | 按正确的顺序返回包含该队列中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |

</figure>

### java.util.AbstractCollection 类中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [包含所有(收藏<？> c)](https://www.geeksforgeeks.org/abstractcollection-containsall-method-in-java-with-examples/) | 如果此集合包含指定集合中的所有元素，则返回 true。 |
| [【isempty()](https://www.geeksforgeeks.org/abstractcollection-isempty-method-in-java-with-examples/) | 如果此集合不包含元素，则返回 true。 |
| [toString()](https://www.geeksforgeeks.org/abstractcollection-tostring-method-in-java-with-examples/) | 返回此集合的字符串表示形式。 |

</figure>

### java.util.AbstractQueue 类中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [加(E e)](https://www.geeksforgeeks.org/abstractqueue-add-method-in-java-with-examples/) | 如果可以在不违反容量限制的情况下立即将指定的元素插入到该队列中，成功时返回 true，如果当前没有可用空间，则抛出 IllegalStateException。 |
| [addAll(收藏<？延伸 E > c)](https://www.geeksforgeeks.org/abstractqueue-addall-method-in-java-with-examples/) | 将指定集合中的所有元素添加到该队列中。 |
| [元素()](https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/) | 检索但不移除该队列的头。 |
| [移除()](https://www.geeksforgeeks.org/abstractqueue-remove-method-in-java-with-examples/#:~:text=The%20remove()%20method%20of,the%20head%20of%20this%20queue.&text=Parameters%3A%20This%20method%20does%20not,if%20the%20queue%20is%20empty.) | 检索并删除该队列的头。 |

</figure>

### 接口 Java . util . concurrent . blockingqueue 中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [加(E e)](https://www.geeksforgeeks.org/blockingqueue-add-in-java-with-examples/#:~:text=The%20add(E%20e)%20method,insertion%2C%20it%20returns%20an%20IllegalStateException.) | 如果可以在不违反容量限制的情况下立即将指定的元素插入到该队列中，成功时返回 true，如果当前没有可用空间，则抛出 IllegalStateException。 |
| [轮询(长超时，时间单位单位)](https://www.geeksforgeeks.org/blockingqueue-poll-method-in-java-with-examples/) | 检索并删除该队列的头，如果需要某个元素变得可用，则等待指定的等待时间。 |
| [取()](https://www.geeksforgeeks.org/blockingqueue-take-method-in-java-with-examples/) | 检索并移除该队列的头，如有必要，等待直到某个元素变得可用。 |

</figure>

### 接口 java.util.Collection 中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| addAll(集合〔t0〕c) | 将指定集合中的所有元素添加到此集合中(可选操作)。 |
| 包含所有(集合> c) | 如果此集合包含指定集合中的所有元素，则返回 true。 |
| 等于(对象 0) | 将指定的对象与此集合进行比较，看是否相等。 |
| hashCode() | 返回此集合的哈希代码值。 |
| isEmpty() | 如果此集合不包含元素，则返回 true。 |
| 并行流() | 以此集合为源返回一个可能并行的流。 |
| 流() | 返回以此集合为源的顺序流。 |
| toArray (IntFunction <t>生成器)</t> | 使用提供的生成器函数分配返回的数组，返回包含此集合中所有元素的数组。 |

</figure>

### 接口 java.util.Queue 中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [元素()](https://www.geeksforgeeks.org/queue-element-method-in-java/) | 检索但不移除该队列的头。 |
| [peek()](https://www.geeksforgeeks.org/queue-peek-method-in-java/) | 检索但不移除该队列的头，如果该队列为空，则返回 null。 |
| [投票()](https://www.geeksforgeeks.org/queue-poll-method-in-java/) | 检索并删除该队列的头，如果该队列为空，则返回 null。 |
| [移除()](https://www.geeksforgeeks.org/queue-remove-method-in-java/) | 检索并删除该队列的头。 |

</figure>

**参考:**[https://docs . Oracle . com/en/Java/javase/11/docs/API/Java . base/Java/util/concurrent/linkedblockingqueue . html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/concurrent/LinkedBlockingQueue.html)