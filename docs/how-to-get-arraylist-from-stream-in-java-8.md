# 如何在 Java 8 中从 Stream 获取数组列表

> 原文:[https://www . geesforgeks . org/how-to-ArrayList-from-stream-in-Java-8/](https://www.geeksforgeeks.org/how-to-get-arraylist-from-stream-in-java-8/)

给定一个流，任务是将这个流转换成 Java 8 中的数组列表。

**示例:**

```
Input: Stream: [1, 2, 3, 4, 5]
Output: ArrayList: [1, 2, 3, 4, 5]

Input: Stream: ['G', 'e', 'e', 'k', 's']
Output: ArrayList: ['G', 'e', 'e', 'k', 's']

```

1.  **Using Collectors.toList() method**:
    1.  获取要转换的流。
    2.  使用 Collect()和 Collectors.toList()方法将流收集为列表。
    3.  将此列表转换为数组列表
    4.  返回/打印数组列表

    下面是上述方法的实现:

    **程序:**

    ```
    // Java program to convert Stream to ArrayList
    // using Collectors.toList() method

    import java.util.*;
    import java.util.stream.*;

    public class GFG {

        // Function to get ArrayList from Stream
        public static <T> ArrayList<T>
        getArrayListFromStream(Stream<T> stream)
        {

            // Convert the Stream to List
            List<T>
                list = stream.collect(Collectors.toList());

            // Create an ArrayList of the List
            ArrayList<T>
                arrayList = new ArrayList<T>(list);

            // Return the ArrayList
            return arrayList;
        }

        // Driver code
        public static void main(String args[])
        {

            Stream<Integer>
                stream = Stream.of(1, 2, 3, 4, 5);

            // Convert Stream to ArrayList in Java
            ArrayList<Integer>
                arrayList = getArrayListFromStream(stream);

            // Print the arraylist
            System.out.println("ArrayList: " + arrayList);
        }
    }
    ```

    **Output:**

    ```
    ArrayList: [1, 2, 3, 4, 5]

    ```

2.  **Using Collectors.toCollection() method:**
    **Approach:**
    1.  获取要转换的流。
    2.  使用 Collect()和 Collectors.toCollection()方法将流收集为数组列表。
    3.  返回/打印数组列表

    下面是上述方法的实现:

    **程序:**

    ```
    // Java program to convert Stream to ArrayList
    // using Collectors.toList() method

    import java.util.*;
    import java.util.stream.*;

    public class GFG {

        // Function to get ArrayList from Stream
        public static <T> ArrayList<T>
        getArrayListFromStream(Stream<T> stream)
        {

            // Convert the Stream to ArrayList
            ArrayList<T>
                arrayList = stream
                                .collect(Collectors
                                .toCollection(ArrayList::new));

            // Return the ArrayList
            return arrayList;
        }

        // Driver code
        public static void main(String args[])
        {

            Stream<Integer>
                stream = Stream.of(1, 2, 3, 4, 5);

            // Convert Stream to ArrayList in Java
            ArrayList<Integer>
                arrayList = getArrayListFromStream(stream);

            // Print the arraylist
            System.out.println("ArrayList: "
                               + arrayList);
        }
    }
    ```

    **Output:**

    ```
    ArrayList: [1, 2, 3, 4, 5]

    ```