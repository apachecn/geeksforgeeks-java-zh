# 如何在 Java 中通过索引从 LinkedHashMap 中获取一个值？

> 原文:[https://www . geesforgeks . org/如何通过 java 中的索引从 linkedhashmap 获取值/](https://www.geeksforgeeks.org/how-to-get-a-value-from-linkedhashmap-by-index-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的预定义类，类似于 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) ，包含键及其各自的值与 HashMap 不同，在 LinkedHashMap 中插入顺序被保留。任务是通过它们的索引，换句话说，它们的插入顺序，从 LinkedHashMap 中获取值。作为 LinkedHashMap 的一个优点，我们知道它们的插入顺序是保留的，它们的顺序将与插入的顺序相同。

**例:**

```java
Input : Key - 2 : Value - 5
    Key - 4 : Value - 3
    Key - 1 : Value - 10
    Key - 3 : Value - 12
    Key - 5 : Value - 6

Input Index ( assuming index from 1-N ) :

Index - 2

Output :  3 ( Value 3 is at Index 2 )
```

**算法:**

```java
1\. Check whether the index in LinkedHashMap does exist or not. 
By using size of LinkedHashMap.

2\. If exists a print, the value present there.

    else print " index does not exist ".
```

**方法 1(使用键数组):**

您可以使用[键集](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/)方法将 LinkedHashMap 的所有键转换为一个集合，然后使用[到数组](https://www.geeksforgeeks.org/set-toarray-method-in-java-with-example/)方法将该集合转换为一个数组，现在使用数组索引访问该键并从 LinkedHashMap 中获取值。

**语法:**

```java
Object[] toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含与集合相似元素的数组。

**示例**

## Java

```java
// Java program to get a value from LinkedHashMap by index
// Using Array
import java.util.*;
import java.io.*;

public class GFG {

    public static void main(String[] args)
    {

        // create linked hash map instance
        LinkedHashMap<Integer, Integer> lhm
            = new LinkedHashMap<Integer, Integer>();

        // Add mappings
        lhm.put(2, 5);
        lhm.put(4, 3);
        lhm.put(1, 10);
        lhm.put(3, 12);
        lhm.put(5, 6);

        // get the key set
        Set<Integer> keySet = lhm.keySet();

        Integer[] keyArray
            = keySet.toArray(new Integer[keySet.size()]);

        // taking input of index
        Integer index = 2;
        Integer key = keyArray[index - 1];

        // get value from the LinkedHashMap for the key
        System.out.println("Value at index " + index
                           + " is : " + lhm.get(key));
    }
}
```

**输出**

```java
Value at index 2 is : 3
```

**方法 2(使用列表):**

该方法与第一种方法类似，您可以将键转换为[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)或[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)，而不是转换为数组。

**示例**

## Java

```java
// Java program to get a value from LinkedHashMap by index
// Using ArrayList

import java.util.*;
import java.io.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an instance of linked hash mao
        LinkedHashMap<Integer, Integer> lhm
            = new LinkedHashMap<Integer, Integer>();

        // Add mappings
        lhm.put(2, 5);
        lhm.put(4, 3);
        lhm.put(1, 10);
        lhm.put(3, 12);
        lhm.put(5, 6);

        // get the key set
        Set<Integer> keySet = lhm.keySet();

        // Integer[] keyArray = keySet.toArray(new
        // Integer[keySet.size()]); replacing array with
        // ArrayList here.
        List<Integer> listKeys
            = new ArrayList<Integer>(keySet);

        Integer index = 2; // taking input of index
        Integer key = listKeys.get(index - 1);

        // get value from the LinkedHashMap for the key
        System.out.println("Value at index " + index
                           + " is : " + lhm.get(key));
    }
}
```

**输出**

```java
Value at index 2 is : 3
```

**方法 3(使用迭代器):**

我们可以使用 [entrySet()](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 方法获取 LinkedHashMap 的所有条目，并使用 For-each 循环计数迭代它们，直到它等于 index，break 并打印该值。

**示例**

## Java

```java
// Java program to get a value from LinkedHashMap by index
// Using iterator

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // create an instance of linked hashmap
        LinkedHashMap<Integer, Integer> lhm
            = new LinkedHashMap<Integer, Integer>();

        // Add mappings
        lhm.put(2, 5);
        lhm.put(4, 3);
        lhm.put(1, 10);
        lhm.put(3, 12);
        lhm.put(5, 6);

        // get all entries from the LinkedHashMap
        Set<Map.Entry<Integer, Integer> > entrySet
            = lhm.entrySet();

        // create an iterator
        Iterator<Map.Entry<Integer, Integer> > iterator
            = entrySet.iterator();

        int i = 0;
        int index = 1;
        int value = 0;

        while (iterator.hasNext()) {

            if (index - 1 == i) {
                value = iterator.next()
                            .getValue(); // index is found
                                         // get value
                break; // at that index and break
            }

            iterator.next();
            i++;
        }
        // print value
        System.out.println("Value at index " + index + " : "
                           + value);
    }
}
```

**输出**

```java
Value at index 1 : 5
```

**时间复杂度:** O(n)

**注意:**不建议使用方法 1 和方法 2，因为它们需要分配一个新的数组或 ArrayList 来执行这个需要更多空间的任务，而是使用只需要迭代的迭代器方法(Direct 方法)。