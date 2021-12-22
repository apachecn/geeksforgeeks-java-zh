# 将指定集合中的数据添加到当前集合中的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-add-the-data-from-specific-collection-in-current-collection/](https://www.geeksforgeeks.org/java-program-to-add-the-data-from-the-specified-collection-in-the-current-collection/)

将对象分组在一个单元中称为集合。例如数组、列表、哈希集等。可以使用 Java 中的[**【addAll()**](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/)方法从当前集合中的指定集合添加数据。该方法属于头文件 [**java.util.*** 。](https://www.geeksforgeeks.org/java-util-package-java/)如果在调用方法后集合的添加成功，则 **addAll()** 方法返回真值，否则返回假值。

我们可以通过两种方式使用 **addAll()** 方法，即:

*   静态方法
*   实例方法

假设有两个列表。

**静态方法声明**

```
Collections.addAll(List1,List2)
```

**实例方法声明**

让列表 1 中需要插入列表 2 的索引为 1。

```
List1.addAll(1, List2);
```

**addAll()** 方法总是抛出以下异常:

*   [**【NullPointRexception】**](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)**:**如果指定的或当前集合具有空值，则会引发此异常。
*   **IllegalArgumentException:**如果指定集合的参数具有阻止将它们添加到当前集合的值，则会引发此异常。

**例 1:**

```
Input: boolean b = List1.addAll(large,extra-large)

If the appending is successful
Output: true 

If the appending is unsuccessful
Output: false
```

**例 2:**

```
Input:  Collections.addAll(List1,List2)
Output: List1 = [small,medium,large,extra-large]
```

**采用的方法:**

*   初始化两个集合。
*   使用 **addAll()** 方法追加列表。
*   检查方法调用的布尔值。
*   打印集合的最终值。

以下是上述方法的**实现方式**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Add the Data from the Specified
// Collection in the Current Collection

import java.util.*;
public class AddCollections {
    public static void main(String[] args)
    {
        // Creating object of a list which is our current
        // collection
        ArrayList<Integer> list = new ArrayList<Integer>();

        // Adding values to the initial list
        list.add(1);
        list.add(2);
        list.add(3);

        // Printing the initial list
        System.out.println(
            "Initial collection value of list: " + list);

        // creating object of the specified list.
        ArrayList<Integer> list2 = new ArrayList<Integer>();

        list2.add(4);
        list2.add(5);
        list2.add(6);

        // Printing the initial list
        System.out.println(
            "Initial collection value of list2: " + list2);

        // returns true if addition is successful else
        // false
        // adding data from the specified collection in
        // the  current collection at a specified position
        boolean b = list.addAll(2, list2);

        // printing the boolean result
        System.out.println("Boolean Result: " + b);

        // printing the final list with the new values added
        System.out.println(
            "Final collection value of list: " + list);

        // creating an object for a different collection

        Integer[] arr = new Integer[4];

        // Initializing the array
        arr[0] = 9;
        arr[1] = 8;
        arr[2] = 7;
        arr[3] = 6;

        // Adding array elements to list2
        Collections.addAll(list2, arr);

        // Printing the new List2
        System.out.println(
            "Final collection value of list2: " + list2);
    }
}
```

**Output**

```
Initial collection value of list: [1, 2, 3]
Initial collection value of list2: [4, 5, 6]
Boolean Result: true
Final collection value of list: [1, 2, 4, 5, 6, 3]
Final collection value of list2: [4, 5, 6, 9, 8, 7, 6]
```