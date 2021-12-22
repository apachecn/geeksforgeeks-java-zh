# 如何检查 Java 中的 LinkedHashMap 大小？

> 原文:[https://www . geesforgeks . org/how-check-the-link edhashmap-size-in-Java/](https://www.geeksforgeeks.org/how-to-check-the-linkedhashmap-size-in-java/)

[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)的大小可以通过多种方式获得，比如使用内置函数和迭代链接哈希表。

**示例:**

```
Input : List : [1 : "John", 2 : "Tom", 3 : "Tim"]
Output: 3

Input : List : [1 : "John", 2 : "Tom"]
Output: 2
```

**方法 1:使用迭代**

1.  创建一个整数数据类型的大小变量，并用 0 初始化它。
2.  开始遍历 LinkedHashMap，并在每次迭代时增加大小变量。
3.  迭代完成后，打印尺寸可变。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find the size of LinkedHashMap
import java.util.*;
public class LinkedHashMapSizeExample {

    public static void main(String[] args)
    {

        // LinkedHashMap Initialization
        LinkedHashMap<Integer, String> lhMapColors
            = new LinkedHashMap<Integer, String>();

        lhMapColors.put(1, "red");
        lhMapColors.put(2, "white");
        lhMapColors.put(3, "blue");

        // Create of size variable and initialize with 0
        int size = 0;
        for (Map.Entry mapElement :
             lhMapColors.entrySet()) {
            size++;
        }
        System.out.println("Size of LinkedHashMap is "
                           + size);
    }
}
```

**Output**

```
Size of LinkedHashMap is 3
```

**方法二:使用大小()方法**

**语法:**

```
List.size()
```

**返回类型:**

```
Integer
```

1.  创建整数数据类型的大小变量，并使用 size()方法对其进行初始化。
2.  打印尺寸可变。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find the size of LinkedHashMap
import java.util.LinkedHashMap;
public class LinkedHashMapSizeExample {

    public static void main(String[] args)
    {
        // Initialize LinkedHashMap
        LinkedHashMap<Integer, String> lhMapColors
            = new LinkedHashMap<Integer, String>();

        // Add elements
        lhMapColors.put(1, "red");
        lhMapColors.put(2, "white");
        lhMapColors.put(3, "blue");

        // Create size variable and initialize
        // it with size() method
        int size = lhMapColors.size();
        System.out.println("Size of LinkedHashMap is "
                           + size);
    }
}
```

**Output**

```
Size of LinkedHashMap is 3
```