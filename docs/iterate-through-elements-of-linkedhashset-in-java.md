# 遍历 Java 中 LinkedHashSet 的元素

> 原文:[https://www . geesforgeks . org/iterate-through-elements-of-link edhashset-in-Java/](https://www.geeksforgeeks.org/iterate-through-elements-of-linkedhashset-in-java/)

[**链接的 HashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 [**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 的有序版本，它维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。

**例:**

```java
Input: 
["Geeks", "for", "Geeks"]

Output:
Geeks
for
Geeks

Input: 
[9, 4, 6, 2, 8]

Output:
9
4
6
2
8
```

**迭代链接的不同方式 HashSet 元素:**

1.  Use for-for-each loop
2.  Using iterators
3.  Use JDK 1.8 stream

**方法 1:** 使用[进行每个循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate through linkedHashset
// Using the for-each loop

import java.io.*;
import java.util.LinkedHashSet;

class GFG {
    public static void main(String[] args)
    {

        LinkedHashSet<String> gfg
            = new LinkedHashSet<String>();

        // Adding element to LinkedHashSet
        gfg.add("Geeks");
        gfg.add("for");
        gfg.add("geeks");

        // iterating LinkedHashSet using enhanced for loop
        for (String itr : gfg) {
            System.out.println(itr);
        }
    }
}
```

**Output**

```java
Geeks
for
geeks
```

**方法 2:使用迭代器**

使用[**迭代器方法**](https://www.geeksforgeeks.org/iterators-in-java/) **遍历 LinkedHashSet 的元素。**我们将使用 **hasNext()** 方法和 **next()** 方法以及 while 循环来迭代 LinkedHashSet 元素。

**类型参数:**

*   **e** –the element type maintained by this collection.

**语法:**

```java
public Iterator<E> iterator()
```

**返回:**这个方法按照与输入相同的顺序返回 LinkedHashSet 的元素。

## Java

```java
// Java code to demonstrate 
// the iterating over LinkedHashSet 
// Using iterators

import java.io.*; 
import java.util.*; 

class IteratingLinkedHashSet { 

    public static void main(String[] args) 
    { 
        // Instantiate an object of Set 
        // Since LinkedHashSet implements Set 
        // Set points to LinkedHashSet 
        Set<String> gfg = new LinkedHashSet<String>(); 

        // Elements are added using add() method 
        gfg.add("Geek"); 
        gfg.add("For"); 
        gfg.add("Geeks"); 
        gfg.add("Courses"); 
        gfg.add("Interview Prep"); 
        gfg.add("Doubt Classes"); 

        // Iterating through the LinkedHashSet 
        Iterator itr = gfg.iterator(); 

        while (itr.hasNext()){
              System.out.println( itr.next() );
        }
    }
}
```

**输出**

```java
Geek
For
Geeks
Courses
Interview Prep
Doubt Classes
```

**方法三:使用 JDK 1.8** [**溪流**](https://www.geeksforgeeks.org/stream-in-java/#:~:text=Introduced%20in%20Java%208%2C%20the,to%20produce%20the%20desired%20result.&text=Streams%20don't%20change%20the,as%20per%20the%20pipelined%20methods.)

使用forEach 方法迭代 LinkedHashSet 的元素。我们将使用**流遍历整个内容。**流表示来自源的对象序列，支持聚合操作。

**语法:**

```java
set.stream().forEach()
```

**返回:**返回以集合为源的顺序流。

## Java

```java
// Java code to demonstrate
// the iterating over LinkedHashSet
// Using JDK 1.8 streams

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        LinkedHashSet<Integer> gfg = new LinkedHashSet<Integer>();

        // Elements are added using add() method
        gfg.add(9);
        gfg.add(7);
        gfg.add(11);
        gfg.add(43);
        gfg.add(2);

        // Using forEach Method using Stream.
        gfg.stream().forEach(System.out::println);
    }
}
```

**输出**

```java
9
7
11
43
2
```

**时间复杂度:** O(N)，其中 N 是 LinkedHashSet 的元素个数。