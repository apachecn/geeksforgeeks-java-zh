# 用 Java 创建包含 n 个指定对象副本的列表

> 原文:[https://www . geesforgeks . org/create-list-contain-n-copy-of-specified-object-in-Java/](https://www.geeksforgeeks.org/create-list-containing-n-copies-of-specified-object-in-java/)

要创建一个包含指定[对象](https://www.geeksforgeeks.org/classes-objects-java/)、**n 个副本的 Java 列表，可以使用[**Java . util . collections**](https://www.geeksforgeeks.org/collections-in-java-2/)类的**方法。nCopies()方法接受两个参数——列表长度和列表中需要复制 n 次的对象。

**示例:**

```
Input : n = 4, Object = "Hello"
Output: listOfObjects = ["Hello", "Hello", "Hello", "Hello"]

Input : n = 3, Object = 3
Output: listOfObjects = [3, 3, 3]
```

**申报:**

```
public static nCopies(int length, Object object)
```

**返回值:**包含指定对象的 n 个副本的不可变列表。

**异常抛出:***IllegalArgumentException*
如果提供的长度小于 0
，即 n < 0

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Create List containing n Copies
// of Specified Object in java
import java.io.*;
import java.util.Collections;
import java.util.List;

class GFG {
    public static void main(String[] args)
    {
        int n = 5;
        Object myObj = "GFG";

        List myList = Collections.nCopies(n, myObj);

        System.out.println(myList);
    }
}
```

**Output**

```
[GFG, GFG, GFG, GFG, GFG]
```