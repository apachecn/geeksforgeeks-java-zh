# Java 中的故障快速和故障安全迭代器

> 原文:[https://www . geesforgeks . org/fail-fast-fail-safe-iterators-Java/](https://www.geeksforgeeks.org/fail-fast-fail-safe-iterators-java/)

在本文中，我将解释那些不会快速迭代的集合的行为。首先，在许多地方，没有一个术语像 Java SE 规范中没有使用这个术语那样具有故障安全特性。我正在使用故障安全来区分故障快速迭代器和非故障快速迭代器。
**并发修改:**编程中的并发修改是指当另一个任务已经在一个对象上运行时，并发修改该对象。例如，在 Java 中，当另一个线程正在迭代集合时修改集合。如果检测到这种行为，一些迭代器实现(包括 JRE 提供的所有通用集合实现)可能会选择抛出*ConcurrentModificationException*。

**Java 中的故障快速和故障安全迭代器**

java 中的迭代器用于迭代 Collection 对象。如果集合中有**结构修改**，Fail-Fast 迭代器会立即抛出*ConcurrentModificationException*。结构修改意味着在线程迭代集合时，从集合中添加、移除任何元素。数组列表上的迭代器，HashMap 类是快速失败迭代器的一些例子。
如果一个集合在迭代时被结构性修改，故障安全迭代器不会抛出任何异常。这是因为，它们对集合的克隆进行操作，而不是对原始集合进行操作，这就是为什么它们被称为故障安全迭代器。CopyOnWriteArrayList 上的迭代器、ConcurrentHashMap 类都是故障安全迭代器的例子。

**失败快速迭代器是如何工作的？**

为了知道集合在结构上是否被修改，快速失败迭代器使用一个名为 *modCount* 的内部标志，该标志在每次修改集合时都会更新。每当快速迭代器获得下一个值时(即使用 *next()* 方法)，快速迭代器都会检查 *modCount* 标志，如果在创建该迭代器后发现 *modCount* 已被修改，它会抛出*concurrentmodificationException*。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// Fail Fast Iterator in Java
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;

public class FailFastExample {
    public static void main(String[] args)
    {
        Map<String, String> cityCode = new HashMap<String, String>();
        cityCode.put("Delhi", "India");
        cityCode.put("Moscow", "Russia");
        cityCode.put("New York", "USA");

        Iterator iterator = cityCode.keySet().iterator();

        while (iterator.hasNext()) {
            System.out.println(cityCode.get(iterator.next()));

            // adding an element to Map
            // exception will be thrown on next call
            // of next() method.
            cityCode.put("Istanbul", "Turkey");
        }
    }
}
```

**输出:**

```
India
Exception in thread "main" java.util.ConcurrentModificationException
    at java.util.HashMap$HashIterator.nextNode(HashMap.java:1442)
    at java.util.HashMap$KeyIterator.next(HashMap.java:1466)
    at FailFastExample.main(FailFastExample.java:18)
```

**快速失败迭代器的要点:**

*   如果一个集合在迭代时被修改，这些迭代器会抛出 ConcurrentModificationException。
*   他们使用原始集合遍历集合的元素。
*   这些迭代器不需要额外的内存。
*   例如:数组列表、向量、哈希映射返回的迭代器。

**注释 1(来自 java-docs):** 迭代器的快速失效行为无法保证，因为一般来说，在存在非同步并发修改的情况下，不可能做出任何硬保证。快速失败迭代器在尽力的基础上抛出*ConcurrentModificationException*。因此，编写一个依赖于这个异常正确性的程序是错误的:迭代器的快速失败行为应该只用于检测错误。
**注 2 :** 如果通过 Iterator *remove()* 方法移除一个元素，不会抛出异常。但是，如果通过特定集合 *remove()* 方法移除，将引发*ConcurrentModificationException*。下面的代码片段将演示这一点:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate remove
// case in Fail-fast iterators

import java.util.ArrayList;
import java.util.Iterator;

public class FailFastExample {
    public static void main(String[] args)
    {
        ArrayList<Integer> al = new ArrayList<>();
        al.add(1);
        al.add(2);
        al.add(3);
        al.add(4);
        al.add(5);

        Iterator<Integer> itr = al.iterator();
        while (itr.hasNext()) {
            if (itr.next() == 2) {
                // will not throw Exception
                itr.remove();
            }
        }

        System.out.println(al);

        itr = al.iterator();
        while (itr.hasNext()) {
            if (itr.next() == 3) {
                // will throw Exception on
                // next call of next() method
                al.remove(3);
            }
        }
    }
}
```

**输出:**

```
[1, 3, 4, 5]
Exception in thread "main" java.util.ConcurrentModificationException
    at java.util.ArrayList$Itr.checkForComodification(ArrayList.java:901)
    at java.util.ArrayList$Itr.next(ArrayList.java:851)
    at FailFastExample.main(FailFastExample.java:28)
```

**故障安全迭代器**

首先，在许多地方，没有一个术语像 Java SE 规范中没有使用这个术语那样具有故障安全特性。我用这个术语来演示快速失败迭代器和非快速失败迭代器之间的区别。这些迭代器复制内部集合(对象数组)，并对复制的集合进行迭代。对迭代器进行的任何结构修改都会影响复制的集合**，而不是原始集合**。因此，原始收藏在结构上保持**不变**。

*   故障安全迭代器允许在迭代集合时修改集合。
*   如果一个集合在迭代时被修改，这些迭代器不会抛出任何异常。
*   他们使用原始集合的副本遍历集合的元素。
*   这些迭代器需要额外的内存来克隆集合。例如:ConcurrentHashMap，CopyOnWriteArrayList

**Java 中的故障安全迭代器示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// Fail Safe Iterator in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.Iterator;

class FailSafe {
    public static void main(String args[])
    {
        CopyOnWriteArrayList<Integer> list
            = new CopyOnWriteArrayList<Integer>(new Integer[] { 1, 3, 5, 8 });
        Iterator itr = list.iterator();
        while (itr.hasNext()) {
            Integer no = (Integer)itr.next();
            System.out.println(no);
            if (no == 8)

                // This will not print,
                // hence it has created separate copy
                list.add(14);
        }
    }
}
```

**输出:**

```
1
3
5
8
```

此外，那些不使用快速失败概念的集合不一定会在内存中创建它的克隆/快照，以避免并发修改异常。例如，在 ConcurrentHashMap 的情况下，它不会在单独的副本上运行，尽管它不是故障快速的。相反，它的语义被官方规范描述为弱一致性(Java 中的内存一致性属性)。下面的代码片段将演示这一点:
**不创建单独副本的故障安全迭代器示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// Fail-Safe Iterator which
// does not create separate copy
import java.util.concurrent.ConcurrentHashMap;
import java.util.Iterator;

public class FailSafeItr {
    public static void main(String[] args)
    {

        // Creating a ConcurrentHashMap
        ConcurrentHashMap<String, Integer> map
            = new ConcurrentHashMap<String, Integer>();

        map.put("ONE", 1);
        map.put("TWO", 2);
        map.put("THREE", 3);
        map.put("FOUR", 4);

        // Getting an Iterator from map
        Iterator it = map.keySet().iterator();

        while (it.hasNext()) {
            String key = (String)it.next();
            System.out.println(key + " : " + map.get(key));

            // This will reflect in iterator.
            // Hence, it has not created separate copy
            map.put("SEVEN", 7);
        }
    }
}
```

**输出**T2】

```
ONE : 1
FOUR : 4
TWO : 2
THREE : 3
SEVEN : 7
```

**注(来自 Java-docs)**:ConcurrentHashMap 返回的迭代器弱一致。这意味着这个迭代器可以容忍并发修改，遍历构造迭代器时存在的元素，并且可以(但不保证)反映构造迭代器后对集合的修改。

**故障快速迭代器和故障安全迭代器的区别**

主要区别在于，与快速失败迭代器相反，安全失败迭代器不会抛出任何异常。这是因为它们处理的是集合的克隆，而不是原始集合，这就是为什么它们被称为故障安全迭代器的原因。