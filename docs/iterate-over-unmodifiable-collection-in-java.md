# 在 Java 中迭代不可修改的集合

> 原文:[https://www . geeksforgeeks . org/iterate-over-unmodified-collection-in-Java/](https://www.geeksforgeeks.org/iterate-over-unmodifiable-collection-in-java/)

[集合](https://www.geeksforgeeks.org/collection-interface-in-java-with-examples/)是一个框架，它提供了一个存储和操作对象组的架构。在 **Java** **Collections** 中，我们对给定的元素集执行搜索、排序、迭代等操作。

**可修改:**可修改是指我们可以对集合数据结构中的元素进行增加、删除、更新等操作。

**示例:** Java List 提供的修改方法包括， [add()](https://www.geeksforgeeks.org/list-add-method-in-java-with-examples/) 方法添加列表中的元素， **replaceall()** 方法更改列表中的元素。

**不可修改:**不可修改是指我们不能对集合数据结构中的元素进行增加、删除、更新。

**示例:**我们可以在任何数据结构之前初始化可修改的类，这样我们就可以防止它更新给定数据结构中的任何元素。我们可以使用[collections . unmodiablecollection(集合)](https://www.geeksforgeeks.org/collections-unmodifiablecollection-method-in-java-with-examples/)创建集合的不可修改视图

**申报**

```java
public static <T> Collection<T> unmodifiableCollection(Collection<? extends T> c)
```

**语法:**

> collections . unmodifielecollection(集合)

**参数:** 该方法以 **集合** 为参数，返回不可修改的视图。

**返回值:** 该方法返回指定集合的 **不可修改视图** 。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate Over Unmodifiable Collection

import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;
import java.util.Iterator;
import java.util.List;

public class GFG {

    public static void main(String args[])
    {
        // create a list
        List<String> list = new ArrayList<String>();

        // add elements
        list.add("welcome");
        list.add("to");
        list.add("geeks for geeks");
        list.add("This");
        list.add("is");
        list.add("Unmodifiable Collection");

        System.out.println("Element are added to the list: "
                           + list.get(2));

        // create a immutable view of the list
        Collection<String> immutableCol
            = Collections.unmodifiableCollection(list);

        // iterator on the immutable list
        Iterator<String> iterator = immutableCol.iterator();

        // print the immutable list
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

**Output**

```java
Element are added to the list: geeks for geeks
welcome
to
geeks for geeks
This
is
Unmodifiable Collection
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate Over Unmodifiable Collection 

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
          // create a vector
        Vector<String> v = new Vector<String>();

          // add elements
        v.add("welcome");
        v.add("to");
        v.add("geeks for geeks");

          // create a immutable vector
        Collection<String> immutableCol
            = Collections.unmodifiableCollection(v);

          // iterate and print elements
        Iterator<String> iterator = immutableCol.iterator();
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

**Output**

```java
welcome
to
geeks for geeks
```

**例 3:** 为 *取消支持例外*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// unmodifiableCollection() method
// for UnsupportedOperationException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of ArrayList<Character>
            ArrayList<String> list = new ArrayList<>();

            // populate the list
            list.add("Geeks");
            list.add("for");

            // printing the list
            System.out.println("Initial list: " + list);

            // getting unmodifiable list
            // using unmodifiableCollection() method
            Collection<String> immutablelist
                = Collections.unmodifiableCollection(list);

            // Adding element to new Collection
            System.out.println(
                "\nTrying to modify"
                + " the unmodifiableCollection");

            immutablelist.add("Geeks");
        }

        catch (UnsupportedOperationException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出**

```java
Initial list: [Geeks, for]
Trying to modify the unmodifiableCollection
Exception thrown : java.lang.UnsupportedOperationException
```