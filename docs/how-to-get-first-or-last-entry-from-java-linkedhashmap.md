# 如何从 Java LinkedHashMap 中获取第一个或最后一个条目？

> 原文:[https://www . geesforgeks . org/how-first-or-last-entry-from-Java-linked hashmap/](https://www.geeksforgeeks.org/how-to-get-first-or-last-entry-from-java-linkedhashmap/)

LinkedHashMap 是 Java 中的一个预定义类，类似于 HashMap，包含键及其各自的值，不像 HashMap，在 LinkedHashMap 中插入顺序是保留的。任务是获取 LinkedHashMap 中出现的第一个和最后一个条目。迭代以获得最后一个和第一个值。“映射”中的第一个和最后一个条目是首先插入的条目，也是最后插入的条目，插入顺序保持不变。

**方法:**

1.  **使用 for-each 循环在地图上迭代的简单方法。**
2.  **将 LinkedHashMap 的键转换为整数数组。**
3.  **将 LinkedHashMap 中的键转换为 List，如 ArrayList 到 LinkedList。**

插图:

> **输入:**
> 
> 键 2:值 5
> 
> 键- 14:值-35
> 
> 键- 31:值-20
> 
> 键- 36:值-18
> 
> 键- 52:值-6
> 
> **输出:**
> 
> 关键字值
> 
> 第一-> 2 5
> 
> 最后-> 52 6

**方法 1:** 使用 for-each 循环在地图上迭代的简单方法。

构造函数 ***getFirst()*** 和 ***getLast()***

*   *getFirst()* 打印第一个条目
*   *getLast()* 移动到最后一个条目(索引等于 LinkedHashMap 的大小)

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to get first or last entry
// from Java LinkedHashMap

// Importing all class of
// java.util package
import java.util.*;
// Importing java input/output classes
import java.io.*;

class GFG {

  // getLast() method
    public static void
    getLast(LinkedHashMap<Integer, Integer> lhm)
    {
        int count = 1;

        for (Map.Entry<Integer, Integer> it :
             lhm.entrySet()) {

            if (count == lhm.size()) {

                System.out.println("Last Key-> "+it.getKey());
              System.out.println("Last Value-> "+it.getValue());
                return;
            }
            count++;
        }
    }

  // getFirst() method to get first element from
  // java LinkedHashMap
    public static void
    getFirst(LinkedHashMap<Integer, Integer> lhm)
    {
        int count = 1;

        for (Map.Entry<Integer, Integer> it :
             lhm.entrySet()) {
            if (count == 1) {
              System.out.println("First Key-> "+it.getKey());
              System.out.println("First Value-> "+it.getValue());
                return;
            }
            count++;
        }
    }

  // Main driver method
    public static void main(String[] args)
    {

      // Creating(defining) a LinkedHashMap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

      // Adding elements to above LinkedHashMap
        LHM.put(2, 5);
        LHM.put(14, 35);
        LHM.put(36, 20);
        LHM.put(34, 18);
        LHM.put(52, 6);

      // Calling getFirst() method in main()
        getFirst(LHM);

      // Calling getLast() method in main()
        getLast(LHM);
    }
}
```

**Output**

```java
First Key-> 2
First Value-> 5
Last Key-> 52
Last Value-> 6
```

时间复杂度:0(n)

**方法 2:** 将 LinkedHashMap 的键转换为整数数组。

**算法:**

*   获取与键对应的第一个和值。
*   打印与键对应的最后一个值。

```java
Pseudo Code :
Integer[] aKeys = LHM.keySet().toArray(new Integer[LHM.size()]);
// where LHM is name of LinkedHashMap created and aKeys of array to be converted.
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to get first or last entry
// from Java LinkedHashMap
// By converting Map to integer array

// Importing all class of
// java.util package
import java.util.*;
// Importing java input/output classes
import java.io.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a LinkedHashMAp
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

        // Adding. elements to above LinkedHashMap
        // Custom inputs
        LHM.put(1, 8);
        LHM.put(2, 6);
        LHM.put(3, 7);
        LHM.put(4, 2);
        LHM.put(5, 5);

        // Getting all keys from the LinkedHashMap, and
        // converting it to an array
        Integer[] aKeys
            = LHM.keySet().toArray(new Integer[LHM.size()]);

        // Condition check
        // If array is having element
        // Print key and value
        if (aKeys.length > 0) {

            // Print first key and first value
            // From integer array
            System.out.println("First key-> " + aKeys[0]);
            System.out.println("First value-> "
                               + LHM.get(aKeys[0]));

            // Print first key from integer array
            System.out.println("Last key-> "
                               + aKeys[aKeys.length - 1]);

            // Print last value from integer array
            System.out.println(
                "Last value-> "
                + LHM.get(aKeys[aKeys.length - 1]));
        }
    }
}
```

**Output**

```java
First key-> 1
First value-> 8
Last key-> 5
Last value-> 5
```

时间复杂度:0(1)

**方法 3:** 将 LinkedHashMap 中的键转换为 List，如 ArrayList 到 LinkedList。

**算法**

*   首先获取与该键对应的值。
*   打印最后一个和对应键的值。

```java
Pseudo Code:
List<Integer> lKeys = new ArrayList<Integer>(LHM.keySet());
// where LHM is name of LinkedHashMap and 
         lKeys is name of List
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to get first or last entry
// from Java LinkedHashMap
// By converting Map to List

// Importing all class of
// java.util package
import java.util.*;
// Importing java input/output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a LinkedHashMapc
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

        // Adding elements to above LinkedHashMap
        // Custom inputs
        LHM.put(1, 8);
        LHM.put(2, 6);
        LHM.put(3, 7);
        LHM.put(4, 2);
        LHM.put(5, 5);

        // Creating a List
        List<Integer> lKeys
            = new ArrayList<Integer>(LHM.keySet());

        // Condition check
        // If there is single element in List
        // Print key and value
        if (lKeys.size() > 0) {

            // Print first key form List
            System.out.println("First key: "
                               + lKeys.get(0));

            // Print first value from List
            System.out.println("First value: "
                               + LHM.get(lKeys.get(0)));

            // Print last key from List
            System.out.println(
                "Last key: " + lKeys.get(lKeys.size() - 1));

            // Print last value from List
            System.out.println(
                "Last value: "
                + LHM.get(lKeys.get(lKeys.size() - 1)));
        }
    }
}
```

**Output**

```java
First key: 1
First value: 8
Last key: 5
Last value: 5
```

时间复杂度:0(1)