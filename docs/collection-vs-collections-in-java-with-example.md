# Java 中的集合与集合，示例

> 原文:[https://www . geesforgeks . org/collection-vs-collection-in-Java-with-example/](https://www.geeksforgeeks.org/collection-vs-collections-in-java-with-example/)

**Collection:** Collection 是 java.util.package 中存在的一个[接口](https://www.geeksforgeeks.org/interfaces-in-java/)，用于将一组单独的对象表示为一个单元。它类似于 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 语言中的容器。集合被认为是集合框架的根接口。它提供了几个类和接口来将一组单独的对象表示为一个单元。

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)、[集合](https://www.geeksforgeeks.org/set-in-java/)、[队列](https://www.geeksforgeeks.org/queue-interface-java/)是采集界面的主要子界面。map 接口也是 java 集合框架的一部分，但是它不继承接口的集合。 **add()** 、 **remove()** 、 **clear()** 、 **size()** 、 **contains()** 是采集界面的重要方法。

**申报:**

```java
public interface Collection<E> extends Iterable<E>

Type Parameters: E - the type of elements returned by this iterator

```

**Collections:** Collections 是 java.util.package 中存在的一个实用类，它定义了排序和搜索等多种实用方法，用于对 collection 进行操作。它有所有静态方法。这些方法为开发人员提供了急需的便利，允许他们有效地使用[收集框架](https://www.geeksforgeeks.org/collections-in-java-2/)。例如，它有一个方法 *sort()* 按照默认的排序顺序对集合元素进行排序，它有一个方法 *min()* ，和 *max()* 分别找出集合元素中的最小值和最大值。

**申报:**

```java
public class Collections extends Object

```

**集合 vs Collections:**

<figure class="table">

| **Set** | **Set** |
| --- | --- |
| It is an interface. | Is a utility class. |
| It is used to represent a group of individual objects as a single unit. | It defines several practical methods for manipulating collections. |
| Collection is an interface that contains static methods since java8\. Interfaces can also contain abstract methods and default methods. | It contains only static methods. |

</figure>

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate the difference  
// between Collection and Collections

import java.io.*;
import java.util.*;

class GFG {

    public static void main (String[] args) 
    {

      // Creating an object of List<String>
      List<String> arrlist = new ArrayList<String>(); 

      // Adding elements to arrlist
      arrlist.add("geeks");
      arrlist.add("for");
      arrlist.add("geeks");

      // Printing the elements of arrlist
      // before operations
      System.out.println("Elements of arrlist before the operations:");
      System.out.println(arrlist);

      System.out.println("Elements of arrlist after the operations:");

      // Adding all the specified elements
      // to the specified collection
      Collections.addAll(arrlist, "web", "site");

      // Printing the arrlist after
      // performing addAll() method
      System.out.println(arrlist);

      // Sorting all the elements of the  
      // specified collection according to 
      // default sorting order
      Collections.sort(arrlist);

      // Printing the arrlist after
      // performing sort() method
      System.out.println(arrlist);

    }
}
```

****Output**

```java
Elements of arrlist before the operations:
[geeks, for, geeks]
Elements of arrlist after the operations:
[geeks, for, geeks, web, site]
[for, geeks, geeks, site, web]

```**