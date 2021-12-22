# Java 中的抽象顺序列表子列表()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-sublist-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-sublist-method-in-java-with-example/)

Java 中**抽象顺序列表**的**子列表()**方法用于获取此列表中指定的 fromIndex(包含)和 toIndex(不包含)之间的部分的视图。(如果 fromIndex 和 toIndex 相等，则返回的列表为空。)返回的列表由该列表支持，因此返回列表中的非结构性变化反映在该列表中，反之亦然。返回的列表支持该列表支持的所有可选列表操作。

**语法:**

```
protected List<E> subList(int fromIndex, 
                                int toIndex)

```

**参数:**这些方法取两个参数:

*   **fromIndex:** 要从中提取元素的起始索引。
*   **到索引:**要从中提取元素的结束索引。(独家)

**返回值:**此方法返回此列表内指定范围的视图
**异常:**此方法抛出:

*   **indexout of BoundSexception**:如果端点索引值超出范围。
*   **IllegalArgumentException** :如果端点索引出现故障。

以下示例说明了 abstractsequentialilist . sublist()方法:

**例 1** :

```
// Java program to demonstrate the
// working of subList() method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // creating an AbstractSequentialList
        AbstractSequentialList<Integer> arr
            = new LinkedList<Integer>();

        // use add() method
        // to add values in the list
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(12);
        arr.add(9);
        arr.add(13);

        // prints the list before removing
        System.out.println("AbstractSequentialList: "
                           + arr);

        // Getting subList of 1st 2 elements
        // using subList() method
        System.out.println("subList of 1st 2 elements: "
                           + arr.subList(0, 2));
    }
}
```

**Output:**

```
AbstractSequentialList: [1, 2, 3, 12, 9, 13]
subList of 1st 2 elements: [1, 2]

```

**例 2:**

```
// Java program to demonstrate the
// working of subList() method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // creating an AbstractSequentialList
        AbstractSequentialList<Integer> arr
            = new LinkedList<Integer>();

        // use add() method
        // to add values in the list
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(12);
        arr.add(9);
        arr.add(13);

        // prints the list before removing
        System.out.println("AbstractSequentialList: "
                           + arr);

        System.out.println("Trying to get "
                           + "subList of 11th elements: ");

        try {

            // Getting subList of 10th
            // using subList() method
            arr.subList(10, 11);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
AbstractSequentialList: [1, 2, 3, 12, 9, 13]
Trying to get subList of 11th elements: 
java.lang.IndexOutOfBoundsException: toIndex = 11

```