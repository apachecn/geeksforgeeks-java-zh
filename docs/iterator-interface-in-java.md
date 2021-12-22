# Java 中的迭代器接口

> 原文:[https://www.geeksforgeeks.org/iterator-interface-in-java/](https://www.geeksforgeeks.org/iterator-interface-in-java/)

Java **迭代器 java [集合](https://www.geeksforgeeks.org/collections-in-java-2/)的**接口允许我们访问集合的元素，用于迭代集合中的元素([地图](https://www.geeksforgeeks.org/map-interface-java-examples/)、[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)或[集合](https://www.geeksforgeeks.org/set-in-java/))。它有助于轻松检索集合的元素并对每个元素执行操作。 [**迭代器**](https://www.geeksforgeeks.org/iterators-in-java/) 是一个通用迭代器，因为它可以应用于任何 Collection 对象。我们只能使用迭代器沿**向前**方向遍历。使用扩展迭代器的**列表迭代器**，可以双向遍历。**读取和移除**操作都可以通过迭代器接口来执行。这包含在 Java JDK 1.2 中。唯一的枚举是 JDK 1.0 中包含的第一个迭代器。要使用迭代器，我们必须导入 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)。

**枚举界面的限制:**

在 Java 集合中，迭代器接口被用来代替枚举。

*   枚举是不是一个通用迭代器，只用于像[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)、[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)这样的遗留类。
*   迭代器允许调用方在元素迭代过程中从给定集合中移除元素。
*   在**枚举**中，只有正向迭代是可能的。

**迭代器接口的声明**

```java
public interface Iterator<E>

```

**E**–该迭代器返回的元素类型

### 迭代器的子接口

**解说:T1**

```java
public interface EventIterator extends Iterator<Event>

```

事件迭代器不可修改。

*方法:* nextEvent()返回事件集中的下一个事件。

**列表迭代器<E>:**T3】

```java
public interface ListIterator<E> extends Iterator<E>

```

列表迭代器，允许向前或向后遍历列表，或者在迭代过程中修改列表，并获得迭代器的当前位置。**列表迭代器**没有当前元素。

**原始迭代器< T，T_CONS >，原始迭代器。原始迭代器。OfLong**

**实现类:**

*   BeanContextSupport。BCSIterator
*   EventReaderDelegate
*   [扫描仪](https://www.geeksforgeeks.org/scanner-class-in-java/)

**示例:迭代器**的实现

集合框架中的所有类都提供[迭代器()](https://www.geeksforgeeks.org/how-to-use-iterator-in-java/)方法，该方法返回迭代器的实例来迭代集合中的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the usage of Iterator()
import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;
public class JavaIteratorExample1 {
    public static void main(String[] args)
    {
          // create a list
        List<String> list = new LinkedList<>();
        list.add("Welcome");
        list.add("to");
        list.add("GFG");

        System.out.println("The list is given as : "
                           + list);

          // get the iterator on the list
        Iterator<String> itr = list.iterator();

        // Returns true if there are more number of
        // elements.
        while (itr.hasNext()) {
            // Returns the next element.
            System.out.println(itr.next());
        }

        // Removes the last element.
        itr.remove();
        System.out.println(
            "After the remove() method is called : "
            + list);
    }
}
```

**Output**

```java
The list is given as : [Welcome, to, GFG]
Welcome
to
GFG
After the remove() method is called : [Welcome, to]
```

**数组列表迭代器示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to iterate over an arraylist
// using Iterator
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // initializing ArrayList
        List<Integer> numbers
            = Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80);

        // Looping ArrayList using Iterator
        Iterator it = numbers.iterator();
        while (it.hasNext())
            System.out.print(it.next() + " ");
    }
}
```

**Output**

```java
10 20 30 40 50 60 70 80 
```

**开发自定义类迭代器**

要为用户定义/自定义类提供类似的功能，我们应该遵循以下步骤:

*   定义自定义类。
*   将集合类定义为此自定义类。
*   集合类应该导入 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包并实现**可迭代**接口。
*   这个集合类现在应该为 Iterable 接口的方法迭代器()提供实现。

**开发自定义类示例代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java program to show the creation of
// custom class that implements iterable interface
import java.util.*;
import java.io.*;
class Employees implements Iterable {

    List<String> str = null;
    public Employees()
    {
        str = new ArrayList<String>();
        str.add("practice");
        str.add("geeks");
        str.add("for");
        str.add("geeks");
        str.add("to");
        str.add("learn");
        str.add("coding");
    }

    // if we are implementing Iterable interface, the we
    // need to define the iterator() method of Iterable
    // interface
    @Override public Iterator<String> iterator()
    {
        return str.iterator();
    }
}

public class EmployeesTester {
    public static void main(String[] args)
    {
        Employees emps = new Employees();
        for (String st : emps.str) {
            System.out.println(st);
        }
    }
}
```

**Output**

```java
practice
geeks
for
geeks
to
learn
coding
```

**使用 remove()方法从集合中移除项目**

*   它移除迭代器返回的集合的最后一个元素。
*   如果迭代正在进行，同时基础集合被修改，那么通过调用 **remove()** 方法，迭代器将抛出**ConcurrentModificationException。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java program to remove()
// elements from a collection

import java.util.ArrayList;
import java.util.Iterator;

public class MyClass {
    public static void main(String[] args)
    {
          // create a list of Integers
        ArrayList<Integer> numbers
            = new ArrayList<Integer>();
        numbers.add(12);
        numbers.add(8);
        numbers.add(2);
        numbers.add(23);

          // get the iterator on the list
        Iterator<Integer> it = numbers.iterator();
        while (it.hasNext()) {

              // gives the next element
              // and iterator moves to next 
              // element
            Integer i = it.next();

            if (i < 10) {

                  // removes the current element
                it.remove(); 
            }
        }
        System.out.println(numbers);
    }
}
```

**Output**

```java
[12, 23]
```

**迭代器 forEachRemaining()示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the usage of
// Iterator forEachRemaining()
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        //  initializing ArrayList
        List<Integer> numbers
            = Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80);

        numbers.iterator().forEachRemaining(
            System.out::println);
    }
}
```

**Output**

```java
10
20
30
40
50
60
70
80

```

**Java 迭代器的优势:**

1.  它不是一个遗留接口，可以遍历像[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)、[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)、[哈希表](https://www.geeksforgeeks.org/hashset-in-java/)等整体集合。
2.  它可以用于任何 java 集合，因此被称为集合的通用游标应用编程接口。
3.  支持读取和删除操作。
4.  简单易用的方法名。

**Java 迭代器的限制:**

1.  它不支持 CRUD(创建、读取、更新、删除)操作中的创建和更新操作。
2.  它只支持单向遍历，即正向遍历。
3.  与[分割器](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)相比，它不支持对大量数据进行更好的迭代。
4.  它只支持顺序迭代，即不支持元素并行迭代。

**迭代器与枚举的区别:**

<figure class="table">、

| 

迭代器

 | 

枚举

 |
| --- | --- |
| It was introduced in JDK 1.2. | Introduced in JDK 1.0. |
| It is a universal cursor, that is, it can be used in any java collection. | It is not a universal cursor, that is, we can only use it for some legacy classes. |
| Read and remove operations are supported. | Only read operations are supported. |
| It has a simple method name. | There are lengthy method names. |
| You can make any changes when traversing the element. | We can't make any changes when crossing. |
| Not a legacy interface. You can traverse the whole set, such as [array list](https://www.geeksforgeeks.org/arraylist-in-java/) , [hashmap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) , [tree set](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) , [vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) and other sets. | Legacy interface. Traverse only [vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) , [hash table](https://www.geeksforgeeks.org/hashtable-in-java/) . |

</figure>

**方法:**

<figure class="table">

| 

**方法**

 | **Type** | **Explanation** |
| --- | --- | --- |
| 哈斯下一步() | Boole | 

*   如果迭代有更多的**元素**，那么**返回真**
*   如果迭代器遍历了所有元素，则返回 false

 |
| 下一个() | E | 

*   它返回**迭代的下一个元素。**
*   如果迭代器没有更多的元素，它将抛出**nosukeelementexception**。

 |
| remove | 空的 | 

*   它**移除迭代器返回的集合的最后一个元素**。
*   如果迭代正在进行，同时底层集合被修改，那么通过调用 remove()方法，迭代器将抛出**Concurrentmodification Exception。**

 |
| foreachrestrict() | E | 

*   它对每个剩余的**元素**执行给定的动作，直到所有元素都被处理。
*   如果指定了顺序，则按照迭代顺序执行操作。
*   如果动作为空，则抛出**空指针异常**。

 |

</figure>