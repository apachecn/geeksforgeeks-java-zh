# Java 中的可迭代接口

> 原文:[https://www.geeksforgeeks.org/iterable-interface-in-java/](https://www.geeksforgeeks.org/iterable-interface-in-java/)

在 JDK 1.5 中引入了**可迭代**接口。属于**爪哇郎**套餐。一般来说，实现 Iterable 的对象允许它被迭代。可迭代接口允许对象成为针对循环(针对每个循环)增强的[的目标。](https://www.geeksforgeeks.org/for-each-loop-in-java/)

**可迭代**的定义

```java
public interface Iterable<T>
{
  Iterator<T>    iterator();

  Spliterator<T> spliterator();

  void           forEach(Consumer<? super T> action);
}

```

这里， **T** 是迭代器返回的元素类型。

**迭代方式**

有三种方法可以迭代**可迭代**的对象。

1.  Use [enhanced for loop](https://www.geeksforgeeks.org/for-each-loop-in-java/) (for-each loop)
2.  Use an iterative [foreach](https://www.geeksforgeeks.org/iterable-foreach-method-in-java-with-examples/) loop.
3.  Use the interface of **iterator < T >**

**使用增强 for 循环迭代可迭代的**

实现集合接口的类的对象可以使用[进行迭代，对于每个](https://www.geeksforgeeks.org/for-each-loop-in-java/)循环，集合接口扩展了可迭代接口。

## Java

```java
// Java Program to demonstrate iterate 
// an iterable using for-each loop

import java.io.*;
import java.util.*;

class IterateUsingEnhancedForLoop {
    public static void main (String[] args) {

      // create a list
      List<String> list = new ArrayList<String>();

      // add elements
      list.add("Geeks");
      list.add("for");
      list.add("Geeks");

      // Iterate through the list
      for( String element : list ){
          System.out.println( element );
      }
    }
}
```

**输出**

```java
Geeks
for
Geeks
```

**使用 forEach 循环迭代一个 Iterable】**

[forEach()](https://www.geeksforgeeks.org/iterable-foreach-method-in-java-with-examples/) 方法以[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)为参数。为集合的每个元素调用这个 Lambda 表达式。在下面的例子中，对于列表中的每个**元素**，该函数将该元素打印到控制台。

## Java

```java
// Java Program to demonstrate iterate
// an Iterable using forEach method

import java.io.*;
import java.util.*;

class IterateUsingforEach {
    public static void main(String[] args)
    {
          // create a list
        List<String> list = new ArrayList<>();

          // add elements to the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

          // Iterate through the list
        list.forEach(
            (element) -> { System.out.println(element); });
    }
}
```

**输出**

```java
Geeks
for
Geeks
```

**使用迭代器**迭代可迭代对象

我们可以通过使用**迭代器()方法**从 Java Iterable 中获取迭代器来迭代它的元素。

使用迭代器遍历集合执行操作时使用的方法有:

*   **[hasnext ()]** : If we have reached the end of the set, we will return false, otherwise we will return true.
*   **Next ()** : Returns the next element in the set.
*   **Remove ()** : Remove the last element returned by the iterator from the collection.
*   **Foreach Restrict ()** : Perform a given operation on each remaining element in the set in sequence.

## 爪哇

```java
// Java Program to demonstrate iterate
// an Iterable using an Iterator

import java.io.*;
import java.util.*;

class IterateUsingIterator {
    public static void main(String[] args)
    {
        List<String> list = new ArrayList<>();

        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        Iterator<String> iterator = list.iterator();

        while (iterator.hasNext()) {
            String element = iterator.next();
            System.out.println(element);
        }
    }
}
```

**输出**

```java
Geeks
for
Geeks
```

### 可迭代的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [forEach(消费者<？超级 T >动作)](https://www.geeksforgeeks.org/iterable-foreach-method-in-java-with-examples/) | Performs a given action on each element of Iterable until all elements are processed or the action throws an exception. |
| iterator | An iterator that returns an element of type t. |
| Splitter | Create a [splitter](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/) on the element described by this Iterable. |

</figure>

**必须阅读**

*   [Implement iterator and iterable interface](https://www.geeksforgeeks.org/java-implementing-iterator-and-iterable-interface/) in Java
*   [Iterator](https://www.geeksforgeeks.org/iterators-in-java/)

**参考:**[https://docs . Oracle . com/en/Java/javase/11/docs/API/Java . base/Java/lang/Iterable . html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Iterable.html)