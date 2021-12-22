# 如何在 Java 的 LinkedHashSet 中找到元素索引？

> 原文:[https://www . geeksforgeeks . org/如何找到元素-索引-in-linkedhashset-in-java/](https://www.geeksforgeeks.org/how-to-find-the-element-index-in-linkedhashset-in-java/)

[LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 用于存储不同的项目，并获取项目在 Java 中插入的顺序。LinkedHashSet 不存储基于索引的值。但是在 Java 的 LinkedHashSet 中有一些查找元素索引的方法。

**方法 1:(通过将 LinkedHashSet 转换为 ArrayList)**

通过将 LinkedHashSet 转换为[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)来查找 Java 中 LinkedHashSet 中的元素索引，过程分为两部分:

**1。**使用构造函数将 LinkedHashSet 转换为 ArrayList。

```
// Convert LinkedHashSet to ArrayList using constructor
ArrayList<Integer> elements = new ArrayList<>(set);
```

**2。**使用 Java 中的 [indexOf()](https://www.geeksforgeeks.org/java-util-arraylist-indexof-java/) 方法获取元素索引。

**语法:**

```
public int indexOf(Object o)
```

**参数:**该函数只有一个参数，即列表中要搜索的元素。

**返回:**此方法返回列表中给定元素第一次出现的索引，如果该元素不在列表中，则返回“-1”。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find the element
// index in LinkedHashSet
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty HashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(30);
        set.add(20);
        set.add(50);

        // Convert LinkedHashSet to ArrayList
        ArrayList<Integer> elements = new ArrayList<>(set);

        // Print the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Print index of all the elements
        for (Integer x : elements) {
            System.out.println("Index of " + x + ": "
                               + elements.indexOf(x));
        }

        // It returns -1 becouce 60 not present in
        // LinkedHashSet
        System.out.println("Index of " + 60 + ": "
                           + elements.indexOf(60));
    }
}
```

**Output**

```
LinkedHashSet: [10, 20, 50, 30]
Index of 10: 0
Index of 20: 1
Index of 50: 2
Index of 30: 3
Index of 60: -1
```

**方法 2:(使用迭代器或** [增强为循环](https://www.geeksforgeeks.org/for-each-loop-in-java/) **)**

为了在 Java 中找到元素索引，我们可以创建一个新的用户定义函数(indexOf)，返回给定的元素索引。我们的函数迭代 LinkedHashSet 并返回给定元素的索引。

**注意:**如果该元素不存在于 LinkedHashSet 中，则返回-1。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find the 
// element index in LinkedHashSet
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty HashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(30);
        set.add(20);
        set.add(50);

        // Print the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Print index of elements
        for (Integer x : set) {
            System.out.println("Index of " + x + ": "
                               + indexOf(set, x));
        }

        // It returns -1 becouce it is not present in
        // LinkedHashSet
        System.out.println("Index of " + 60 + ": "
                           + indexOf(set, 60));
    }

    public static int indexOf(LinkedHashSet<Integer> set,
                              int element)
    {

        // If element not present in the LinkedHashSet it
        // returns -1
        int index = -1;

        // get an iterator
        Iterator<Integer> iterator = set.iterator();

        int currentIndex = 0;
        while (iterator.hasNext()) {

            // If element present in the LinkedHashSet
            if (iterator.next().equals(element)) {
                index = currentIndex;
                break;
            }

            currentIndex++;
        }

        // Return index of the element
        return index;
    }
}
```

**Output**

```
LinkedHashSet: [10, 20, 50, 30]
Index of 10: 0
Index of 20: 1
Index of 50: 2
Index of 30: 3
Index of 60: -1
```

**方法 3:(使用数组)**使用数组在 Java 中查找 LinkedHashSet 中的元素索引，过程分为两部分:

**1。**使用[到数组()](https://www.geeksforgeeks.org/linkedhashset-toarray-method-in-java-with-example/)方法将链接的哈希集转换为数组。

```
// New Array

Integer[] array = new Integer[set.size()];

// Convert set to Array using toArray

array = set.toArray(array);
```

**2。**使用索引查找元素。

**语法:**

```
Object[] arr = LinkedHashSet.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个数组，该数组包含类似于 LinkedHashSet 的元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find the 
// element index in LinkedHashSet
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty HashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(30);
        set.add(20);
        set.add(50);

        // Print the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // New Array
        Integer[] array = new Integer[set.size()];

        // Convert LinkedHashSet to Array
        array = set.toArray(array);

        // Print index of elements
        for (int i = 0; i < array.length; i++) {
            System.out.println("Index of " + array[i] + ":"
                               + i);
        }

        int element = 50;

        int index = -1;

        for (int i = 0; i < array.length; i++) {

            // if element is equal to array value
            // store index and come out
            if (array[i] == element) {
                index = i;
                break;
            }
        }

        // print index
        System.out.println("Index of " + element
                           + " is : " + index);
    }
}
```

**Output**

```
LinkedHashSet: [10, 20, 50, 30]
Index of 10:0
Index of 20:1
Index of 50:2
Index of 30:3
Index of 50 is : 2
```