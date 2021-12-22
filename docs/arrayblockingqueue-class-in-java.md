# Java 中的 ArrayBlockingQueue 类

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-class-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)

**ArrayBlockingQueue** 类是一个由数组支持的有界阻塞队列。通过有界，这意味着队列的大小是固定的。一旦创建，容量就不能更改。试图将元素放入完整队列将导致操作阻塞。同样，从空队列中获取元素的尝试也会被阻止。ArrayBlockingQueue 的边界最初可以绕过容量作为 ArrayBlockingQueue 构造函数中的参数来实现。该队列对元素**先进先出**进行排序。这意味着该队列的头部是该队列中存在的元素中最老的元素。

这个队列的尾部是这个队列元素的最新元素。新插入的元素总是被插入到队列的尾部，队列检索操作在队列的头部获取元素。

这个类及其迭代器实现了**集合**和**迭代器**接口的所有可选方法。这个类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员。

**数组锁定队列的层次结构**

![Hierarchy of ArrayBlockingQueue](img/b28b008c354089a45145cb0e09bd46ee.png)

该类扩展了[抽象队列<E>T1】并实现了**可序列化**、**可迭代<E>T5】、**集合<E>T7】、****](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)****[阻塞队列<E>T9】、](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/)[队列<E>T11】接口。](https://www.geeksforgeeks.org/queue-interface-java/)****

**申报**

> 公共类 ArrayBlockingQueue <e>扩展抽象队列<e>实现阻塞队列<e>，可序列化</e></e></e>

这里， **E** 是集合中存储的元素类型。

### ArrayBlockingQueue 的构造函数

在这里，**的容量**是的阵列阻塞队列的大小。

**1。ArrayBlockingQueue(int capacity):**创建具有给定(固定)容量和默认访问策略的 ArrayBlockingQueue。

> ArrayBlockingQueue <e>abq =新的 ArrayBlockingQueue<e>(int capacity)；</e></e>

**2。ArrayBlockingQueue(int capacity，boolean fair):** 创建一个具有给定(固定)容量和指定访问策略的 ArrayBlockingQueue。如果公平值为真，则按先进先出顺序处理插入或移除时被阻止的线程的队列访问；如果为 false，则访问顺序未指定。

> ArrayBlockingQueue <e>abq =新的 ArrayBlockingQueue<e>(int capacity，boolean fair)；</e></e>

**3。ArrayBlockingQueue(int capacity，boolean fair，Collection c):** 创建一个 ArrayBlockingQueue，具有给定(固定)容量、指定的访问策略，并且最初包含给定集合的元素，按照集合迭代器的遍历顺序添加。如果公平值为真，则按先进先出顺序处理插入或移除时被阻止的线程的队列访问；如果为 false，则访问顺序未指定。

> ArrayBlockingQueue <e>abq =新 ArrayBlockingQueue<e>(int capacity，boolean fair，Collection c)；</e></e>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate 
// ArrayBlockingQueue(int initialCapacity)
// constructor

import java.util.concurrent.ArrayBlockingQueue;

public class ArrayBlockingQueueDemo {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 15;

        // create object of ArrayBlockingQueue
        // using ArrayBlockingQueue(int initialCapacity) constructor
        ArrayBlockingQueue<Integer> abq = new ArrayBlockingQueue<Integer>(capacity);

        // add  numbers
        abq.add(1);
        abq.add(2);
        abq.add(3);

        // print queue
        System.out.println("ArrayBlockingQueue:" + abq);
    }
}
```

**Output:** 

```java
ArrayBlockingQueue:[1, 2, 3]
```

### 基本操作

**1。添加元素**

[add(E e)](https://www.geeksforgeeks.org/arrayblockingqueue-add-method-in-java/) 方法将作为参数传递的元素插入到该队列尾部的方法中。如果添加元素超出了队列的容量，那么该方法将抛出一个**非法状态异常**。如果元素的添加成功，此方法返回 true，否则将引发 IllegalStateException。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate adding
// elements to an ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;

public class AddingElementsExample {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 15;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> abq = new ArrayBlockingQueue<Integer>(capacity);

        // add  numbers
        abq.add(1);
        abq.add(2);
        abq.add(3);

        // print queue
        System.out.println("ArrayBlockingQueue:" + abq);
    }
}
```

**Output**

```java
ArrayBlockingQueue:[1, 2, 3]
```

**2。拆卸元件**

[移除(对象 o)](https://www.geeksforgeeks.org/arrayblockingqueue-remove-method-in-java/) 方法从该队列中移除指定元素的单个实例(如果存在)。我们可以说，如果这个队列包含一个或多个这样的元素，那么这个方法会移除一个元素 e，使得 o 等于(e)。如果此队列包含我们要移除的指定元素，Remove()方法将返回 true。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate removal of 
// elements from an AbstractQueue

import java.util.concurrent.ArrayBlockingQueue;

public class RemovingElementsExample {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 15;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> abq = new ArrayBlockingQueue<Integer>(capacity);

        // add  numbers
        abq.add(1);
        abq.add(2);
        abq.add(3);

        // print queue
        System.out.println("ArrayBlockingQueue:" + abq);

        // remove 223
        boolean response = abq.remove(2);

        // print Queue
        System.out.println("Removal of 2 :" + response);

        // print Queue
        System.out.println("queue contains " + abq);

        // remove all the elements
        abq.clear();

        // print queue
        System.out.println("ArrayBlockingQueue:" + abq);
    }
}
```

**Output**

```java
ArrayBlockingQueue:[1, 2, 3]
Removal of 2 :true
queue contains [1, 3]
ArrayBlockingQueue:[]
```

**3。访问元素**

使用**队列**接口提供的 [peek()](https://www.geeksforgeeks.org/arrayblockingqueue-peek-method-in-java/) 方法返回队列头。它检索但不删除该队列的头。如果队列为空，则此方法返回 null。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate accessing
// elements of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class AccessingElementsExample {

    public static void main(String[] args)
    {

        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new ArrayBlockingQueue<Integer>(capacity);

        // Add element to ArrayBlockingQueue
        queue.add(23);
        queue.add(32);
        queue.add(45);
        queue.add(12);

        // Print queue after adding numbers
        System.out.println("After addding numbers queue is ");
        System.out.println(queue);

        // Print head of queue using peek() method
        System.out.println("Head of queue " + queue.peek());
    }
}
```

**Output**

```java
After addding numbers queue is 
[23, 32, 45, 12]
Head of queue 23
```

**4。穿越**

**ArrayBlockingQueue** 类的[迭代器()](https://www.geeksforgeeks.org/arrayblockingqueue-iterator-method-in-java/#:~:text=The%20iterator()%20method%20of,returned%20iterator%20is%20weakly%20consistent.)方法用于以适当的顺序返回与该队列相同元素的迭代器。从这个方法返回的元素包含从第一个(头)到最后一个(尾)的元素。返回的迭代器弱一致。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate iterating
// over ArrayBlockingQueue.

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;

public class TraversingExample {

    public static void main(String[] args)
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue = new ArrayBlockingQueue<String>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer("User");
        queue.offer("Employee");
        queue.offer("Manager");
        queue.offer("Analyst");
        queue.offer("HR");

        // Print queue
        System.out.println("Queue is " + queue);

        // Call iterator() method and Create an iterator
        Iterator iteratorValues = queue.iterator();

        // Print elements of iterator
        System.out.println("\nThe iterator values:");
        while (iteratorValues.hasNext()) {
            System.out.println(iteratorValues.next());
        }
    }
}
```

**Output**

```java
Queue is [User, Employee, Manager, Analyst, HR]

The iterator values:
User
Employee
Manager
Analyst
HR
```

### 数组锁定队列的方法

在这里， **E** 是这个集合中持有的元素类型

<figure class="table">

| 

METHOD

 | 

DESCRIPTION

 |
| --- | --- |
| [加(E)](https://www.geeksforgeeks.org/arrayblockingqueue-add-method-in-java/) | Insert the specified element at the end of this queue. If possible, insert it immediately without exceeding the queue capacity, successfully return true and throw illeggal. |
| [晴()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-clear-method-in-java/&sa=U&ved=2ahUKEwjJw__y2fnrAhXszzgGHRVkDAI4ChAWMAF6BAgIEAE&usg=AOvVaw1yWHGwWMuc1AF2sODsbM9N) | Automatically remove all elements from this queue. |
| [包含(对象 o)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-contains-method-in-java/&sa=U&ved=2ahUKEwjQ6_Wy2fnrAhUf83MBHWTAC2IQFjAHegQIBRAB&usg=AOvVaw1-0zPK_K6mYHFkrNxJz5wl) | Returns true if the queue contains the specified element. |
| [Drainage map (collection <? super E > c)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-drainto-method-in-java/&sa=U&ved=2ahUKEwjQ6_Wy2fnrAhUf83MBHWTAC2IQFjAEegQIBBAB&usg=AOvVaw3t75LIGFGLuVs4LVDC2lRk) | Remove all available elements from this queue and add them to the given collection. |
| [排水至(收藏<？超 E > c，int maxElements)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-drainto-method-in-java/&sa=U&ved=2ahUKEwjQ6_Wy2fnrAhUf83MBHWTAC2IQFjAEegQIBBAB&usg=AOvVaw3t75LIGFGLuVs4LVDC2lRk) | Remove up to a given number of available elements from this queue and add them to a given collection. |
| ForEach (consumer action) | Execute a given action on each element of Iterable until all elements are processed or the action throws an exception. |
| [Iterator ()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-iterator-method-in-java/&sa=U&ved=2ahUKEwjJw__y2fnrAhXszzgGHRVkDAI4ChAWMAN6BAgHEAI&usg=AOvVaw1YcAaweJ_1LFCU8iqtZ-mx) | Iterators that return elements in this queue in the correct order. |
| [报价(东/东)](https://www.geeksforgeeks.org/arrayblockingqueue-offer-method-in-java/) | If it is possible to insert the specified element immediately without exceeding the capacity of the queue, insert the specified element at the end of the queue, and return true if the queue is full, otherwise return false. |
| [报价(东 E、长超时，时间单位单位)](https://www.geeksforgeeks.org/arrayblockingqueue-offer-method-in-java/) | Insert the specified element at the end of this queue until the specified waiting time. If the queue is full, the waiting space becomes available. |
| [放(E E)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-put-method-in-java/&sa=U&ved=2ahUKEwjQ6_Wy2fnrAhUf83MBHWTAC2IQFjAFegQIAhAB&usg=AOvVaw26FWJCqoOSdPrCLGRseJgv) | Insert the specified element at the end of this queue. If the queue is full, wait for the space to become available. |
| 剩余容量() | Returns the number of additional elements that the queue can ideally accept without blocking (without memory or resource constraints). |
| [Remove (object o)](https://www.geeksforgeeks.org/arrayblockingqueue-remove-method-in-java/#:~:text=The%20remove(Object%20o)%20method,one%20or%20more%20such%20elements.) | Removes a single instance of the specified element from the queue, if it exists. |
| Remove all (set c) | Optionally, remove all elements of the specified collection contained in the collection. |
| RemoveIf (predicate filter) | Removes all elements in this collection that satisfy the given predicate. |
| Retail (collection c) | Keep only the elements in this collection that are contained in the specified collection (optional operation). |
| [尺寸()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-size-method-in-java/&sa=U&ved=2ahUKEwjJw__y2fnrAhXszzgGHRVkDAI4ChAWMAJ6BAgJEAE&usg=AOvVaw3OIBKtmQYKbAcphp0vJqyc) | Returns the number of elements in the queue. |
| [分流器()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-spliterator-method-in-java/&sa=U&ved=2ahUKEwjJw__y2fnrAhXszzgGHRVkDAI4ChAWMAR6BAgFEAI&usg=AOvVaw1kCgeHhN7piQetUKtGrZC5) | Returns the Spliterator of the elements in this queue. |
| [到数组()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-toarray-method-in-java/&sa=U&ved=2ahUKEwjQ6_Wy2fnrAhUf83MBHWTAC2IQFjAIegQIARAC&usg=AOvVaw3na6JLncaU8ExH5FWsx07H) | Returns an array containing all the elements in the queue in the appropriate order. |
| [至数组(T[]a)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/arrayblockingqueue-toarray-method-in-java/&sa=U&ved=2ahUKEwjQ6_Wy2fnrAhUf83MBHWTAC2IQFjAIegQIARAC&usg=AOvVaw3na6JLncaU8ExH5FWsx07H) | Returns an array containing all elements in the queue in proper order; The runtime type of the returned array is the runtime type of the specified array. |

</figure>

### java.util.AbstractQueue 类中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [addAll(收藏<？延伸 E > c)](https://www.geeksforgeeks.org/abstractqueue-addall-method-in-java-with-examples/) | 将指定集合中的所有元素添加到该队列中。 |
| [元素()](https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/) | 检索但不移除该队列的头。 |
| [移除()](https://www.geeksforgeeks.org/abstractqueue-remove-method-in-java-with-examples/#:~:text=The%20remove()%20method%20of,the%20head%20of%20this%20queue.&text=Parameters%3A%20This%20method%20does%20not,if%20the%20queue%20is%20empty.) | 检索并删除该队列的头。 |

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

### 接口 Java . util . concurrent . blockingqueue 中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
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
| [移除()](https://www.geeksforgeeks.org/queue-remove-method-in-java/#:~:text=The%20remove()%20method%20of,when%20the%20Queue%20is%20empty.) | 检索并删除该队列的头。 |

</figure>

**结论:** ArrayBlockingQueue 一般用在**线程安全的**环境中，在这种环境中，您希望阻塞单个资源上的两个或多个操作，只允许一个线程。此外，我们可以使用容量限制因子来阻止线程。

**参考:**[https://docs . Oracle . com/en/Java/javase/11/docs/API/Java . base/Java/util/concurrent/arrayblockingqueue . html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/concurrent/ArrayBlockingQueue.html)