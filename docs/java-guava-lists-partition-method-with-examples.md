# Java 番石榴| Lists.partition()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-list-partition-method-with-examples/](https://www.geeksforgeeks.org/java-guava-lists-partition-method-with-examples/)

[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中的**list . partition()**方法用于将原始列表划分为相同大小的子列表。该方法接受两个参数。

**例如:**如果作为参数传递的原始列表是[a，b，c，d，e]，分区大小是 3，那么产生的子列表是[[a，b，c]，[d，e]]。

**语法:**

> 公静<**T**>List<**List<**T**>**>分区(List < **T** >列表，int 大小)

**参数:**该方法接受两个参数:

*   **列表:**根据分区大小划分为子列表的列表。
*   **大小:**每个子列表所需的大小。最后一个子列表的大小可能会更小。

**返回值:**该方法返回连续子列表的列表。每个子列表(可能最后一个除外)的大小都等于分区大小。

**异常:**如果分区大小为非正数，方法*list . partition()*将抛出**T5】IllegalArgumentExceptionT7。**

下面的例子说明了上述方法的实现:

**例 1:**

```java
// Java code to show implementation of
// Guava's Lists.partition() method

import com.google.common.collect.Lists;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a List of Integers
        List<Integer> myList
            = Arrays.asList(1, 2, 3, 4, 5);

        // Using Lists.partition() method to divide
        // the original list into sublists of the same
        // size, which are just views of the original list.
        // The final list may be smaller.
        List<List<Integer> > lists
            = Lists.partition(myList, 2);

        // Displaying the sublists
        for (List<Integer> sublist: lists)
            System.out.println(sublist);
    }
}
```

**Output:**

```java
[1, 2]
[3, 4]
[5]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Lists.partition() method

import com.google.common.collect.Lists;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Characters
        List<Character> myList
            = Arrays.asList('H', 'E', 'L', 'L', 'O',
                            'G', 'E', 'E', 'K', 'S');

        // Using Lists.partition() method to divide
        // the original list into sublists of the same
        // size, which are just views of the original list.
        // The final list may be smaller.
        List<List<Character> > lists
            = Lists.partition(myList, 3);

        // Displaying the sublists
        for (List<Character> sublist: lists)
            System.out.println(sublist);
    }
}
```

**Output:**

```java
[H, E, L]
[L, O, G]
[E, E, K]
[S]

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/collect/list . html # partition-Java . util . list-int-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/collect/Lists.html#partition-java.util.List-int-)