# 将其他集合的所有元素插入到 Java 数组列表的指定索引中

> 原文:[https://www . geesforgeks . org/insert-其他集合的所有元素到指定的 java 索引-arraylist/](https://www.geeksforgeeks.org/insert-all-elements-of-other-collection-to-specified-index-of-java-arraylist/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是集合框架的一部分。它是一个列表，实现了 [java.util.list](https://www.geeksforgeeks.org/list-interface-java-examples/) 界面。数组列表是数组的更好选择，尤其是当你不确定数组大小的时候。与固定大小的数组不同，数组列表可以在需要时增加大小。内部数组列表也使用数组来存储数据。当达到当前容量并需要增长时，会创建一个新阵列，并将元素从旧阵列复制到新阵列。

**示例:**

```java
Input : ArrayList = [a, b, c], Vector = [d, e]
Output: collection = [a, b, c, d, e]

Input : ArrayList = [1, 5, 6], Vector = [2, 3]
Output: collection = [1, 2, 3, 5, 6]
```

**进场:**

1.  [创建一个数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)并在其中添加一些元素
2.  创建一个新的集合，这里我们将创建向量
3.  使用 addAll(index，List)方法将元素添加到数组列表中，该方法将列表插入到该列表的给定索引处。

**语法:**

```java
addAll(int index,Collection c)
```

**参数:**

1.  索引:要插入指定元素的索引。
2.  c:这是包含要添加到此列表中的元素的集合

**描述:**

我们可以使用这个方法在给定的索引处插入集合中的元素。列表中的所有元素都向右移动，以便为集合中的元素留出空间。

下面是问题陈述的实现

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Insert all Elements of Other Collection
// to Specified Index of Java ArrayList
import java.util.*;
public class GFG {
    public static void main(String arg[])
    {
        // Creating ArrayList
        ArrayList<String> obj1 = new ArrayList<String>();

        obj1.add("Australia");

        obj1.add("Brazil");

        obj1.add("France");

        obj1.add("Germany");

        obj1.add("India");

        System.out.println("Elements of ArrayList: "
                           + obj1);

        // Creating collection of vector

        Vector<String> obj2 = new Vector<String>();

        obj2.add("Canada");

        obj2.add("Denmark");

        obj2.add("Egypt");

        System.out.println(
            "Elements of Collection(Vector): " + obj2);

        // inserting all Elements of Other Collection to
        // Specified Index of ArrayList
        obj1.addAll(2, obj2);

        System.out.println(
            "After inserting elements of other collection elements of ArrayList:\n"
            + obj1);
    }
}
```

**Output**

```java
Elements of ArrayList: [Australia, Brazil, France, Germany, India]
Elements of Collection(Vector): [Canada, Denmark, Egypt]
After inserting elements of other collection elements of ArrayList:
[Australia, Brazil, Canada, Denmark, Egypt, France, Germany, India]

```