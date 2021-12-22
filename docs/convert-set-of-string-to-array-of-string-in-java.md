# 将字符串集合转换为 Java 中的字符串数组

> 原文:[https://www . geesforgeks . org/convert-set-of-string-to-array-of-string-in-Java/](https://www.geeksforgeeks.org/convert-set-of-string-to-array-of-string-in-java/)

给定一组字符串，任务是将该组字符串转换为 Java 中的字符串数组。

**示例:**

```java
Input: Set<String>: ["ForGeeks", "A Computer Portal", "Geeks"]
Output: String[]: ["ForGeeks", "A Computer Portal", "Geeks"]

Input: Set<String>: ["G", "e", "k", "s"]
Output: String[]: ["G", "e", "k", "s"]

```

*   **Method 1:** Naive Method.
    1.  获取字符串集。
    2.  创建一个空的字符串数组，其大小与字符串数组的大小相同。
    3.  使用高级 for 循环，将字符串集的每个元素复制到字符串数组中。
    4.  返回或打印字符串数组。

    下面是上述方法的实现:

    ```java
    // Java program to convert
    // Set of Strings to Array of Strings

    import java.util.Arrays;
    import java.util.Set;
    import java.util.HashSet;

    class GFG {

        // Function to convert Set<String> to String[]
        public static String[] convert(Set<String> setOfString)
        {

            // Create String[] of size of setOfString
            String[] arrayOfString = new String[setOfString.size()];

            // Copy elements from set to string array
            // using advanced for loop
            int index = 0;
            for (String str : setOfString)
                arrayOfString[index++] = str;

            // return the formed String[]
            return arrayOfString;
        }

        public static void main(String[] args)
        {

            // Get the Set of String
            Set<String>
                setOfString = new HashSet<>(
                    Arrays.asList("Geeks",
                                  "ForGeeks",
                                  "A Computer Portal"));

            // Print the setOfString
            System.out.println("Set of String: "
                               + setOfString);

            // Convert Set to String array
            String[] arrayOfString = convert(setOfString);

            // Print the arrayOfString
            System.out.println("Array of String: "
                               + Arrays.toString(arrayOfString));
        }
    }
    ```

    **Output:**

    ```java
    Set of String: [ForGeeks, A Computer Portal, Geeks]
    Array of String: [ForGeeks, A Computer Portal, Geeks]

    ```