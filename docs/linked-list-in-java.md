# Java 中的链接列表

> 原文:[https://www.geeksforgeeks.org/linked-list-in-java/](https://www.geeksforgeeks.org/linked-list-in-java/)

链表是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。这个类是[链接列表数据结构](https://www.geeksforgeeks.org/data-structures/linked-list/)的实现，这是一个线性数据结构，其中元素不存储在连续的位置，每个元素都是一个单独的对象，有数据部分和地址部分。这些元素使用指针和地址进行链接。每个元素都被称为一个节点。由于插入和删除的动态性和容易性，它们比数组更受欢迎。它也有一些缺点，比如节点不能直接访问，相反，我们需要从头开始，通过链接到达我们希望访问的节点。

【LinkedList 在内部是如何工作的？

由于 LinkedList 作为一个动态数组，我们在创建它时不必指定大小，所以当我们动态添加和删除项目时，列表的大小会自动增加。此外，元素不是以连续的方式存储的。因此，没有必要增加尺寸。在内部，链表使用[双链表数据结构](https://www.geeksforgeeks.org/doubly-linked-list/)实现。普通链表和双链表的主要区别在于，双链表包含一个额外的指针，通常称为前一个指针，以及单链表中的下一个指针和数据。

## 链接列表中的构造函数

为了创建一个链接列表，我们需要创建一个链接列表类的对象。LinkedList 类由各种构造函数组成，这些构造函数允许创建列表。以下是该类中可用的构造函数:

**1。LinkedList():** 此构造函数用于创建空链表。如果我们希望创建一个名为 ll 的空链接列表，那么它可以创建为:

```java
LinkedList ll = new LinkedList();  
```

**2。LinkedList(集合 C):** 这个构造函数用于创建一个包含指定集合的所有元素的有序列表，该列表由集合的迭代器返回。如果我们希望创建一个名为 ll 的链接列表，那么它可以创建为:

```java
LinkedList ll = new LinkedList(C);
```

## Java 链接列表的方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [添加(int 索引，E 元素)](https://www.geeksforgeeks.org/java-util-linkedlist-add-method-in-java/) | 此方法在列表中的指定位置插入指定元素。 |
| [加(E e)](https://www.geeksforgeeks.org/java-util-linkedlist-add-method-in-java/) | 此方法将指定的元素追加到此列表的末尾。 |
| [addAll(int index，Collection < E > c)](https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/) | 此方法将指定集合中的所有元素插入到此列表中，从指定位置开始。 |
| [addAll(集合< E > c)](https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/) | 这个方法按照指定集合的迭代器返回的顺序，将指定集合中的所有元素追加到这个列表的末尾。 |
| [add first(e)](https://www.geeksforgeeks.org/linkedlist-addfirst-method-in-java/) | 此方法在列表的开头插入指定的元素。 |
| [add last(e)](https://www.geeksforgeeks.org/linkedlist-addlast-method-in-java/) | 此方法将指定的元素追加到此列表的末尾。 |
| [晴()](https://www.geeksforgeeks.org/linkedlist-clear-method-in-java/) | 此方法从列表中移除所有元素。 |
| [克隆()](https://www.geeksforgeeks.org/linkedlist-clone-method-in-java/) | 这个方法返回这个链表的一个浅拷贝。 |
| [包含(对象 o)](https://www.geeksforgeeks.org/linkedlist-contains-method-in-java/) | 如果此列表包含指定的元素，则此方法返回 true。 |
| [下降畸胎()](https://www.geeksforgeeks.org/linkedlist-descendingiterator-method-in-java-with-examples/) | 这个方法以相反的顺序返回一个迭代器。 |
| [元素()](https://www.geeksforgeeks.org/linkedlist-element-method-in-java-with- examples/) | 此方法检索但不移除此列表的标题(第一个元素)。 |
| [get(int index)](https://www.geeksforgeeks.org/linkedlist-get-method-in-java/) | 此方法返回列表中指定位置的元素。 |
| [getFirst()](https://www.geeksforgeeks.org/java-util-linkedlist-get-getfirst-getlast-java/) | 此方法返回列表中的第一个元素。 |
| [getLast（）](https://www.geeksforgeeks.org/linkedlist-getlast-method-in-java/) | 此方法返回列表中的最后一个元素。 |
| [索引（对象 o）](https://www.geeksforgeeks.org/linkedlist-indexof-method-in-java/) | 此方法返回此列表中指定元素的第一个匹配项的索引，如果此列表不包含该元素，则返回-1。 |
| [最后索引（对象 o）](https://www.geeksforgeeks.org/linkedlist-lastindexof-method-in-java/) | 此方法返回此列表中指定元素最后一次出现的索引，如果此列表不包含该元素，则返回-1。 |
| [列表迭代器(int index)](https://www.geeksforgeeks.org/linkedlist-listiterator-method-in-java/) | 该方法从列表中的指定位置开始，返回列表中元素的列表迭代器(按正确的顺序)。 |
| [报价(E e)](https://www.geeksforgeeks.org/java-util-linkedlist-offer-offerfirst-offerlast-java/) | 此方法添加指定的元素作为此列表的尾部(最后一个元素)。 |
| [投标人](https://www.geeksforgeeks.org/java-util-linkedlist-offer-offerfirst-offerlast-java/) | 此方法在列表的前面插入指定的元素。 |
| [献上〔e〕t1]](https://www.geeksforgeeks.org/java-util-linkedlist-offer-offerfirst-offerlast-java/) | 此方法在此列表的末尾插入指定的元素。 |
| [peek()](https://www.geeksforgeeks.org/java-util-linkedlist-peek-peekfirst-peeklast-java/) | 此方法检索但不移除此列表的标题(第一个元素)。 |
| [peekFirst()](https://www.geeksforgeeks.org/java-util-linkedlist-peek-peekfirst-peeklast-java/) | 此方法检索但不移除此列表的第一个元素，如果此列表为空，则返回 null。 |
| [速览最后（）](https://www.geeksforgeeks.org/java-util-linkedlist-peek-peekfirst-peeklast-java/) | 此方法检索但不移除此列表的最后一个元素，如果此列表为空，则返回 null。 |
| [投票()](https://www.geeksforgeeks.org/java-util-linkedlist-poll-pollfirst-polllast- examples-java/) | 此方法检索并移除此列表的标题(第一个元素)。 |
| [pollFirst()](https://www.geeksforgeeks.org/java-util-linkedlist-poll-pollfirst-polllast- examples-java/) | 此方法检索并移除此列表的第一个元素，如果此列表为空，则返回 null。 |
| [pollLast()](https://www.geeksforgeeks.org/java-util-linkedlist-poll-pollfirst-polllast- examples-java/) | 此方法检索并移除此列表的最后一个元素，如果此列表为空，则返回 null。 |
| [pop()](https://www.geeksforgeeks.org/linkedlist-pop-method-in-java/) | 这个方法从这个列表所代表的堆栈中弹出一个元素。 |
| [推(E e)](https://www.geeksforgeeks.org/linkedlist-push-method-in-java/) | 此方法将一个元素推送到由该列表表示的堆栈上。 |
| [移除()](https://www.geeksforgeeks.org/linkedlist-remove-method-in-java/) | 此方法检索并移除此列表的标题(第一个元素)。 |
| [移除(int index)](https://www.geeksforgeeks.org/linkedlist-remove-method-in-java/) | 此方法移除列表中指定位置的元素。 |
| [移除(物体 o)](https://www.geeksforgeeks.org/linkedlist-remove-method-in-java/) | 如果存在指定元素，此方法将从该列表中移除第一个出现的元素。 |
| [移除第一（）](https://www.geeksforgeeks.org/linkedlist-removefirst-method-in-java/) | 此方法移除并返回列表中的第一个元素。 |
| [移除第一次出现(对象 o)](https://www.geeksforgeeks.org/linkedlist-removefirstoccurrence-method-in- java/) | 此方法移除列表中指定元素的第一个匹配项(从头到尾遍历列表时)。 |
| [移除 Last()](https://www.geeksforgeeks.org/linkedlist-removelast-method-in-java/) | 此方法移除并返回列表中的最后一个元素。 |
| [移除最后一次出现(对象 o)](https://www.geeksforgeeks.org/linkedlist-removelastoccurrence-method-in-java-with-example/) | 此方法移除列表中指定元素的最后一次出现(从头到尾遍历列表时)。 |
| [集合(int 索引，E 元素)](https://www.geeksforgeeks.org/linkedlist-set-method-in-java/) | 此方法用指定的元素替换列表中指定位置的元素。 |
| [尺寸()](https://www.geeksforgeeks.org/linkedlist-size-method-in-java/) | 此方法返回此列表中的元素数量。 |
| [分流器()](https://www.geeksforgeeks.org/linkedlist-spliterator-method-in-java/) | 此方法在此列表中的元素上创建一个后期绑定和故障快速拆分器。 |
| [toaarray()](https://www.geeksforgeeks.org/linkedlist-toarray-method-in-java-with-example/) | 此方法返回一个数组，该数组包含此列表中按正确顺序排列的所有元素(从第一个到最后一个元素)。 |
| [toaarray(t[]a)](https://www.geeksforgeeks.org/linkedlist-toarray-method-in-java-with-example/) | 此方法返回一个数组，该数组包含此列表中按正确顺序排列的所有元素(从第一个到最后一个元素)；返回数组的运行时类型是指定数组的运行时类型。 |
| toString() | 此方法返回一个字符串，该字符串包含此列表中按正确顺序排列的所有元素(从第一个到最后一个元素)，每个元素用逗号分隔，字符串用方括号括起来。 |

</figure>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate
// Implementation of LinekdList
// class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating object of the
        // class linked list
        LinkedList<String> ll = new LinkedList<String>();

        // Adding elements to the linked list
        ll.add("A");
        ll.add("B");
        ll.addLast("C");
        ll.addFirst("D");
        ll.add(2, "E");

        System.out.println(ll);

        ll.remove("B");
        ll.remove(3);
        ll.removeFirst();
        ll.removeLast();

        System.out.println(ll);
    }
}
```

**Output:** 

```java
[D, A, E, B, C]
[A]
```

[![List-ArrayList-in-Java-In-Depth-Study](img/9b5d4717a0bb9dd15d6dc598671940cb.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200624224531/List-ArrayList-in-Java-In-Depth-Study.png)

在上图中，[抽象列表](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)、[复制写数组列表](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)和[抽象顺序列表](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/)是实现列表接口的类。在每个提到的类中都实现了一个单独的功能。它们是:

1.  **抽象列表:**这个类用来实现一个不可修改的列表，对于这个列表只需要扩展这个抽象列表类，只实现 get()和 size()方法。
2.  **copy onwriterarraylist:**这个类实现了列表接口。这是 ArrayList 的增强版本，其中所有的修改(添加、设置、删除等。)是通过制作列表的新副本来实现的。

## 对链接列表执行各种操作

1.  **添加元素**
2.  **更新元素**
3.  **移除元素**
4.  **迭代元素**

让我们看看如何在 LinkedList 上执行一些基本操作，以便更好地理解它，如下所示:

**操作 1:** 添加元素

为了给数组列表添加一个元素，我们可以使用 [add()方法](https://www.geeksforgeeks.org/java-util-linkedlist-add-method-in-java/)。此方法被重载以基于不同的参数执行多个操作。它们是:

*   **add(Object):** 此方法用于在 LinkedList 的末尾添加一个元素。
*   **add(int index，Object):** 此方法用于在 LinkedList 的特定索引处添加元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to add elements
// to a LinkedList

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
        LinkedList<String> ll = new LinkedList<>();

        ll.add("Geeks");
        ll.add("Geeks");
        ll.add(1, "For");

        System.out.println(ll);
    }
}
```

**Output:** 

```java
[Geeks, For, Geeks]
```

**操作 2:** 改变元素

添加元素后，如果我们想改变元素，可以使用 [set()方法](https://www.geeksforgeeks.org/linkedlist-set-method-in-java/)来完成。因为链表是有索引的，所以我们想要改变的元素是由元素的索引来引用的。因此，此方法采用一个索引和需要插入该索引的更新元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to change elements
// in a LinkedList

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
        LinkedList<String> ll = new LinkedList<>();

        ll.add("Geeks");
        ll.add("Geeks");
        ll.add(1, "Geeks");

        System.out.println("Initial LinkedList " + ll);

        ll.set(1, "For");

        System.out.println("Updated LinkedList " + ll);
    }
}
```

**Output:** 

```java
Initial LinkedList [Geeks, Geeks, Geeks]
Updated LinkedList [Geeks, For, Geeks]
```

**操作 3:** 去除元素

为了从链接列表中删除一个元素，我们可以使用 [remove()方法](https://www.geeksforgeeks.org/linkedlist-remove-method-in-java/)。此方法被重载以基于不同的参数执行多个操作。它们是:

*   **移除(对象):**此方法用于简单地从链接列表中移除对象。如果有多个这样的对象，则删除第一个出现的对象。
*   **remove(int index):** 由于链接列表是有索引的，因此该方法采用一个整数值，该整数值只是删除链接列表中特定索引处的元素。删除元素后，元素的索引也会更新，链接列表的对象也会更新，在删除元素后会给出一个新的列表

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to remove elements
// in a LinkedList

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
        LinkedList<String> ll = new LinkedList<>();

        ll.add("Geeks");
        ll.add("Geeks");
        ll.add(1, "For");

        System.out.println(
            "Initial LinkedList " + ll);

        ll.remove(1);

        System.out.println(
            "After the Index Removal " + ll);

        ll.remove("Geeks");

        System.out.println(
            "After the Object Removal " + ll);
    }
}
```

**Output:** 

```java
Initial LinkedList [Geeks, For, Geeks]
After the Index Removal [Geeks, Geeks]
After the Object Removal [Geeks]
```

**操作 4:迭代链表**

有多种方法可以迭代 LinkedList。最著名的方法是结合使用基本 for 循环和 [get()方法](https://www.geeksforgeeks.org/linkedlist-get-method-in-java/)来获取特定索引处的元素，以及高级 for 循环。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to iterate the elements
// in an LinkedList

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
        LinkedList<String> ll
            = new LinkedList<>();

        ll.add("Geeks");
        ll.add("Geeks");
        ll.add(1, "For");

        // Using the Get method and the
        // for loop
        for (int i = 0; i < ll.size(); i++) {

            System.out.print(ll.get(i) + " ");
        }

        System.out.println();

        // Using the for each loop
        for (String str : ll)
            System.out.print(str + " ");
    }
}
```

**Output:** 

```java
Geeks For Geeks 
Geeks For Geeks
```