# 使用 Java Stream

用指定的值初始化单行列表

> 原文:[https://www . geesforgeks . org/initialize-a-in-a-list-in-a-in-a-line-a-a-a-a-a-in-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a](https://www.geeksforgeeks.org/initialize-a-list-in-a-single-line-with-a-specified-value-using-java-stream/)

给定一个值 **N** ，任务是使用[流](https://www.geeksforgeeks.org/stream-in-java/)在 [Java](https://www.geeksforgeeks.org/java-tutorials/) 中的一行中创建一个具有该值 N 的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)。

**示例:**

```
Input: N = 5
Output: [5]

Input: N = GeeksForGeeks
Output: [GeeksForGeeks]

```

**进场:**

*   获取值 N
*   使用[生成()](https://www.geeksforgeeks.org/stream-generate-method-java/)方法生成流
*   使用 [limit()](https://www.geeksforgeeks.org/stream-limit-method-in-java/) 方法将待创建列表的大小设置为 1
*   使用 [map()](https://www.geeksforgeeks.org/stream-map-java-examples/) 方法传递要映射的值
*   使用 [Collectors.toList()](https://www.geeksforgeeks.org/collectors-tolist-method-in-java-with-examples/) 将生成的流转换为 List，并使用 collect()方法进行收集返回

下面是上述方法的实现:

```
// Java program to initialize a list in a single
// line with a specified value using Stream

import java.io.*;
import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to create a List
    // with the specified value
    public static <T> List<T> createList(T N)
    {

        // Currently only one value is taken
        int size = 1;

        return Stream

            // Generate the Stream
            .generate(String::new)

            // Size of the List to be created
            .limit(size)

            // Passing the value to be mapped
            .map(s -> N)

            // Convert the generated stream into List
            .collect(Collectors.toList());
    }

    // Driver code
    public static void main(String[] args)
    {

        int N = 1024;
        System.out.println("List with element "
                           + N + ": "
                           + createList(N));

        String str = "GeeksForGeeks";
        System.out.println("List with element "
                           + str + ": "
                           + createList(str));
    }
}
```

**Output:**

```
List with element 1024: [1024]
List with element GeeksForGeeks: [GeeksForGeeks]

```