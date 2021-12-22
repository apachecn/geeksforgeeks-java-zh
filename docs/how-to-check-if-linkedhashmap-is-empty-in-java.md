# 如何在 Java 中检查 LinkedHashMap 是否为空？

> 原文:[https://www . geesforgeks . org/如何检查-if-link edhashmap-is-empty-in-Java/](https://www.geeksforgeeks.org/how-to-check-if-linkedhashmap-is-empty-in-java/)

**链接哈希表**就像哈希表一样，有一个额外的功能，即维护插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。这里，让我们说明检查 LinkedHashMap 是否为空的不同方法。

**例:**

```
Input : {3=Geeks, 2=For, 1=Geeks} 
Output: Given LinkedHashMap is not empty

Input : {} 
Output: Given LinkedHashMap is empty
```

**1。使用 size()方法:**

1.  Create the variable lhmSize.
2.  In which the size value of LinkedHashMap is stored.
3.  If the size of the given LinkedHashMap is 0, then it is empty.
4.  Otherwise, it is not empty.

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program check if LinkedHashMap is empty or not
import java.util.LinkedHashMap;
public class Main {

    public static void main(String[] args)
    {
        // create an instance of LinkedHashMap
        LinkedHashMap<Integer, String> hm1
            = new LinkedHashMap<Integer, String>();

        //  Using size() method to make comparison
        System.out.println(
            "Given LinkedHashMap is "
            + (hm1.size() == 0 ? "empty" : "not empty"));

        // Add mappings using put method
        hm1.put(3, "Geeks");
        hm1.put(2, "For");
        hm1.put(1, "Geeks");
        int lhmSize = hm1.size();
        if (lhmSize == 0)
            System.out.println(
                "Given LinkedHashMap is empty");
        else
            System.out.println(
                "Given LinkedHashMap is not empty");
    }
}
```

**Output**

```
Given LinkedHashMap is empty
Given LinkedHashMap is not empty

```

**时间复杂度:** O(1)

**2。使用 isEmpty()方法:**

1.  Create boolean variable lhmSize.
2.  Store the return value of the isEmpty () method.
3.  If the size of the given LinkedHashMap is 0, the isEmpty () method will return true.
4.  Otherwise, the method returns false.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program check if LinkedHashMap is empty or not
import java.util.LinkedHashMap;
public class Main {

    public static void main(String[] args)
    {
        // create an instance of LinkedHashMap
        LinkedHashMap<Integer, String> hm1
            = new LinkedHashMap<Integer, String>();

        //  Using isEmpty() method to make comparison
        System.out.println(
            "Given LinkedHashMap is "
            + (hm1.isEmpty() ? "empty" : "not empty"));

        // Add mappings using put method
        hm1.put(3, "Geeks");
        hm1.put(2, "For");
        hm1.put(1, "Geeks");
        boolean lhmSize = hm1.isEmpty();
        if (lhmSize)
            System.out.println(
                "Given LinkedHashMap is empty");
        else
            System.out.println(
                "Given LinkedHashMap is not empty");
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(1)