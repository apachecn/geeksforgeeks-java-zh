# 如何从 LinkedHashSet 中删除用户定义的对象？

> 原文:[https://www . geeksforgeeks . org/如何删除用户定义的对象-from-linkedhashset/](https://www.geeksforgeeks.org/how-to-delete-user-defined-objects-from-linkedhashset/)

[**链接的 HashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 的有序版本，维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。当迭代一个 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 时，顺序是不可预测的，而 LinkedHashSet 让我们按照元素插入的顺序迭代元素。

**示例:**

```java
Input: ["Geeks", "for", "geeks"]
DELETE = "geeks"
Output: "Geeks"
    "for"

Input: [1, 2, 3, 4, 5]
DELETE = 2
Output: [1, 3, 4, 5]
```

**有两种方法可以从 LinkedHashSet 中删除元素:**

1.  使用移除()方法
2.  使用 clear()方法

**方法 1:** [**【移除( <u>)</u>**](https://www.geeksforgeeks.org/linkedhashset-remove-method-in-java/) 方法用于从 LinkedHashSet 对象中删除特定元素。

**语法:**

```java
LinkedHashSet.remove(Object O)
```

**参数:**参数 *O* 属于链接哈希集类型，指定要从链接哈希集中删除的元素。

**返回值:**如果指定的元素存在于 LinkedHashSet 中，该方法返回 True，否则返回 False。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program  to delete user defined 
// objects from LinkedHashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        LinkedHashSet<String> lset
            = new LinkedHashSet<String>();

        // add elements to HashSet
        lset.add("GEEKS");
        lset.add("FOR");
        lset.add("GEEKS");

        // Displaying the LinkedHashSet Before Deleting
        System.out.println("Before deleting an element :");
        System.out.println(lset);

        // remove() method to delete an element from
        // LinkedHashSet
        lset.remove("FOR");

        // Displaying the LinkedHashSet After Deleting
        System.out.println("After deleting an element:");
        System.out.println(lset);
    }
}
```

**Output**

```java
Before deleting an element :
[GEEKS, FOR]
After deleting an element:
[GEEKS]
```

**方法 2:** [清除()方法用于删除 LinkedHashSet 中的所有元素。此调用返回后，集合将为空。](https://www.geeksforgeeks.org/linkedhashset-clear-method-in-java-with-examples/?ref=rp)

**语法:**

```java
public void clear()
```

**返回值:**此方法**不返回**任何东西。

下面举例说明 *clear()* 方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to delete elements
// from LinkedHashSet

import java.util.*;
import java.util.LinkedHashSet;

public class GFG {
    public static void main(String[] args)
    {

        LinkedHashSet<String> l_set
            = new LinkedHashSet<String>();

        // add elements to HashSet
        l_set.add("GEEKS");
        l_set.add("FOR");
        l_set.add("GEEKS");

        // Displaying the LinkedHashSet Before Deleting
        System.out.println("Before deleting an element :");
        System.out.println(l_set);

        // clear() method to delete all element from
        // LinkedHashSet
        l_set.clear();

        // Displaying an empty LinkedHashSet After Deleting
        System.out.println("After deleting all element:");
        System.out.println(l_set);
    }
}
```

**Output**

```java
Before deleting an element :
[GEEKS, FOR]
After deleting all element:
[]
```