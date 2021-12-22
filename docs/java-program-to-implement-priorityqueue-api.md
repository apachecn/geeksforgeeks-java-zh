# 实现优先级队列 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-priorityqueue-api/](https://www.geeksforgeeks.org/java-program-to-implement-priorityqueue-api/)

A [PriorityQueue](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/) 是一种线性数据结构，其中元素根据它们的自然顺序或由构建时在队列中提供的一些自定义比较器进行排序。在 PriorityQueue 中，根据自然排序，队列的前面指向最少的元素，后面指向最大的元素。对于字母优先队列，将考虑它们的 ASCII 值进行排序。

优先级队列的一些重要特征如下:

*   它不允许插入空元素。
*   这是一个无界队列，意味着它的大小可以扩展。
*   它继承了像对象、抽象集合、[抽象队列](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)这样的类。
*   它不是线程安全的。
*   不能为不可比较的对象创建它。

> 各种操作的时间复杂性:
> 
> *   插入和删除是 O(log(n))的顺序
> *   remove()和 contains()方法的顺序为 O(n)
> *   检索操作最快，为 0(1)级

优先级队列类继承队列接口及其所有方法。优先级队列应用编程接口实现了可序列化、可迭代、集合和队列，这可以从下面显示的架构中感知到。

```
Serializable, Iterable<E>, Collection<E>, Queue<E>
```

![](img/06dc01a92635022e52989e0f4169a79a.png)

**语法:**

```
public class PriorityQueue<E> extends AbstractQueue<E> implements Serializable
```

**参数:** E —该队列中保存的元素类型。

**方法:**

<figure class="table">

| 方法 | 类型 | 描述 |
| --- | --- | --- |
| 添加(英、法) | 布尔 | 将元素 e 插入优先级队列 |
| 清除() | 空的 | 从优先级队列中移除所有元素 |
| 包含(对象 0) | 布尔 | 如果它包含指定的元素，则返回 true |
| 迭代器() | 迭代器 | 返回所有元素的迭代器 |
| 移除(对象 o) | 布尔 | 从队列中移除指定的元素 |
| 比较器() | 比较器 | 返回用于对元素排序的自定义比较器 |
| [toaarray()](https://www.geeksforgeeks.org/arraylist-toarray-method-in-java-with-examples/) | 对象[] | 返回包含优先级队列中所有元素的数组。 |
| [peek()](https://www.geeksforgeeks.org/stack-peek-method-in-java/) |  | 返回优先级队列的头部，而不从队列中删除元素 |
| [投票()](https://www.geeksforgeeks.org/queue-poll-method-in-java/) |  | 移除并返回队列头。如果队列为空，则返回 null。 |
| [分流器()](https://www.geeksforgeeks.org/arraydeque-spliterator-method-in-java/) | 分割器 | 对优先级队列中的元素创建后期绑定和故障快速拆分器。 |

</figure>

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to implement Priority Queue API

// Importing all classes from java.util package
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating(Declaring) an object of PriorityQueue of
        // Integer type i.e Integer elements will be
        // inserted in above object
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        // Adding elements to the object created above
        // Custom inputs
        pq.add(89);
        pq.add(67);
        pq.add(78);
        pq.add(12);
        pq.add(19);

        // Printing the head of the PriorityQueue
        // using peek() method of Queues
        System.out.println("PriorityQueue Head:"
                           + pq.peek());

        // Display message
        System.out.println("\nPriorityQueue contents:");

        // Defining the iterator to traverse over elements of
        // object
        Iterator i = pq.iterator();

        // Condition check using hasNext() method which hold
        // true till single element is remaining in List
        while (i.hasNext()) {

            // Printing the elements of object
            System.out.print(i.next() + " ");
        }

        // Removing random element from above elements added
        // from the PriorityQueue
        // Custom removal be element equals 12
        pq.remove(12);

        // Display message
        System.out.print("\nPriorityQueue contents:");

        // Declaring iterator to traverse over object
        // elements
        Iterator it = pq.iterator();

        // Condition check using hasNext() method which hold
        // true till single element is remaining in List
        while (it.hasNext()) {

            // Printing the elements
            System.out.print(it.next() + " ");
        }

        // Removing all the elements from the PriorityQueue
        // using clear() method
        pq.clear();

        // Adding another different set of elements
        // to the Queue object
        // Custom different inputs
        pq.add(5);
        pq.add(7);
        pq.add(2);
        pq.add(9);

        // Checking a random element just inserted
        // using contains() which returns boolean value
        System.out.print("The queue has 7 = "
                         + pq.contains(7));

        // Display message for content in Priority queue
        System.out.print("\nPriorityQueue contents:");

        // Converting PriorityQueue to array
        // using toArray() method
        Object[] arr = pq.toArray();

        // Iterating over the array elements
        for (int j = 0; j < arr.length; j++) {

            // Printing all the elements in the array
            System.out.print(arr[j] + " ");
        }
    }
}
```

**Output**

```
PriorityQueue Head:12

PriorityQueue contents:
12 19 78 89 67 
PriorityQueue contents:19 67 78 89 The queue has 7 = true
PriorityQueue contents:2 7 5 9 
```