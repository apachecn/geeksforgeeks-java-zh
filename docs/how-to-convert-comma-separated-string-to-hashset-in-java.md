# 如何在 Java 中将逗号分隔的字符串转换成 HashSet？

> 原文:[https://www . geesforgeks . org/how-convert-逗号分隔字符串到 java 中的 hashset/](https://www.geeksforgeeks.org/how-to-convert-comma-separated-string-to-hashset-in-java/)

给定一组字符串，任务是在 Java 中将该组字符串转换为逗号分隔的字符串。

**示例:**

```
Input: Set<String> = ["Geeks", "ForGeeks", "GeeksForGeeks"]
Output: "Geeks, For, Geeks"

Input: Set<String> = ["G", "e", "e", "k", "s"]
Output: "G, e, e, k, s" 
```

**我们有两种方法可以将逗号分隔的字符串转换成 Java HashSet :**

**方法 1:使用字符串分割方法和数组类**

*   首先，我们用逗号分隔字符串，这将返回一个数组。
*   一旦我们得到一个数组，我们将使用 Arrays 类的 asList()方法把它转换成 List。
*   然后可以使用**哈希集**构造函数将列表对象转换为**哈希集**。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert comma 
// separated string to HashSet

import java.util.Arrays;
import java.util.HashSet;
import java.util.List;

public class StringToHashSetExample {

    public static void main(String[] args) {

        String str = "1,2,3,4,2,5";

        // split the string by comma
        String[] strParts = str.split(",");

        // convert array to the List using asList method
        List<String> listParts = Arrays.asList(strParts);

        // create HashSet from the List using constructor
        HashSet<String> hsetFromString = new HashSet<String>( listParts );

        System.out.println("HashSet contains: " + hsetFromString);
    }
}
```

**Output**

```
HashSet contains: [1, 2, 3, 4, 5]
```

**方法二:使用 Java 8 流**

*   如果您使用的是 Java 版本 8 或更高版本，也可以使用流将逗号分隔的字符串转换为下面给出的 Set <string>对象。</string>

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert comma
// separated string to HashSet

import java.util.*;
import java.io.*;
import java.util.stream.*;

public class StringToHashSetExample {

    public static void main(String[] args)
    {

        String str = "1,2,3,4,2,5";

        Set<String> set
            = Stream.of(str.trim().split("\\s*,\\s*"))
                  .collect(Collectors.toSet());

        System.out.println("HashSet contains: " + set);
    }
}
```

**Output**

```
HashSet contains: [1, 2, 3, 4, 5]
```