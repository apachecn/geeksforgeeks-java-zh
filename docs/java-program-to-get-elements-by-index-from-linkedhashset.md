# 从 LinkedHashSet 获取索引元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-elements-by-index-from-link edhashset/](https://www.geeksforgeeks.org/java-program-to-get-elements-by-index-from-linkedhashset/)

[LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 Java 中的一个预定义类，类似于 HashSet。与哈希集不同，在链接中，哈希集的插入顺序被保留。为了从 Java 中的 LinkedHashSet 按索引获取元素，我们有多种方法。

插图:

```
Input      : 2, 3, 4, 2, 7;
Processing : index = 4;
Output     : Element at index 4 is : 7
```

**方法:**

1.  一种使用迭代计数方法的简单方法
2.  将[链接的哈希集转换为数组](https://www.geeksforgeeks.org/linkedhashset-toarrayt-method-in-java-with-example/)
3.  将链接哈希集转换为[列表](https://www.geeksforgeeks.org/arraylist-in-java/)

**方法 1:** 朴素方法使用迭代法进行索引计数并获取给定索引处的元素。

**算法**

1.  使用迭代器遍历我们的 LinkedHashSet。
2.  启动输出索引指针 currentindex = 0
3.  使用 while 循环开始迭代，如果当前索引等于给定索引，则打印元素。

```
Pseudo Code: 
Iterator<Integer> it = LHS.iterator();
while(it.hasNext()) {}
```

**实施:**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Elements by Index from LinkedHashSet
// Using iteration count method

// Importing generic java libraries
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)

    {
        // Adding elements to LinkedHashSet
        // Custom inputs
        LinkedHashSet<Integer> LHS = new LinkedHashSet<>();
        LHS.add(2);
        LHS.add(3);
        LHS.add(4);
        LHS.add(2);
        LHS.add(7);

        // Custom index chosen to get the element
        // present at that index
        int index = 4;

        Iterator<Integer> it = LHS.iterator();

        // Assigning initial values
        int currIndex = 0;
        Integer CurrentElement = null;

        // Condition check using hasNext(), whick
        // returns true if another token as input
        while (it.hasNext()) {

            // next element using iterator is
            // assigned to variable
            CurrentElement = it.next();

            // Variable condition check
            if (currIndex == index - 1) {
                System.out.println("Element at index "
                                   + index + " is : "
                                   + CurrentElement);
                break;
            }

            // If condition fails, so
            // Incrementing current index
            currIndex++;
        }
    }
}
```

**Output**

```
Element at index 4 is : 7
```

> **时间复杂度:** O(n)

**方法 2:** 将 LinkedHashSet 转换为 Array，通过 Array 可以在给定的索引处访问元素。

**算法:**

1.  使用 [*到*](https://www.geeksforgeeks.org/arraylist-toarray-method-in-java-with-examples/) 的方法将给定的链接数据集转换为数组。
2.  访问数组中给定索引上的元素。

```
Pseudo Code:
Integer[] LHSArray = new Integer[LHS.size()];
LHSArray = LHS.toArray(LHSArray);
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Elements by Index from LinkedHashSet
// By converting LinkedHashSet to Array

// Importing generic java libraries
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a LinkedHashSet
        LinkedHashSet<Integer> LHS = new LinkedHashSet<>();

        // Adding elements() to LinkedHashSet
        LHS.add(2);
        LHS.add(3);
        LHS.add(4);
        LHS.add(2);
        LHS.add(7);

        // Custom index chosen from LinkedHashSet
        int index = 4;

        // Converting LnkedHashMap to Array
        Integer[] LHSArray = new Integer[LHS.size()];
        LHSArray = LHS.toArray(LHSArray);

        // Printing desired value at index in array,
        // chosen above index from LinkedHashap
        System.out.println("Element at index " + index
                           + " is : "
                           + LHSArray[index - 1]);
    }
}
```

**Output**

```
Element at index 4 is : 7
```

> 时间复杂度:0(1)

**方法 3:** 将 LinkedHashSet 转换为 List，在给定的索引处获取想要的元素。

**算法**

1.  将我们的链接哈希表转换为类似数组列表的列表。
2.  使用 [*get()方法*](https://www.geeksforgeeks.org/array-get-method-in-java/) 获取给定索引中的元素。

```
Pseudo Code :List<Integer> LHSList =new ArrayList<>(LHS);
              where LHS is name of our LinkedHashSet
```

**实施**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Elements by Index from LinkedHashSet
// By converting LinkedHashSet to List

// Importing java generic libraries
import java.util.*;
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a LinkedHashSet
        LinkedHashSet<Integer> LHS = new LinkedHashSet<>();

        // Adding elements to LinkedHashSet
        LHS.add(2);
        LHS.add(3);
        LHS.add(4);
        LHS.add(2);
        LHS.add(7);

        // Custom index chosen to retrieve value
        int index = 4;

        // Converting LinkedHashSet to List
        Iterator<Integer> it = LHS.iterator();

        // Assigning initial values
        int currIndex = 0;
        Integer CurrentElement = null;

        // Condition check using hasNext(), whick
        // returns true if another token as input
        while (it.hasNext()) {
            CurrentElement = it.next();

            if (currIndex == index - 1) {

                // Printing desired value at index in array,
                // chosen above index from LinkedHashap
                System.out.println("Element at index "
                                   + index + " is : "
                                   + CurrentElement);
                break;
            }

            // Incrementing the current index
            currIndex++;
        }
    }
}
```

**Output**

```
Element at index 4 is : 7
```