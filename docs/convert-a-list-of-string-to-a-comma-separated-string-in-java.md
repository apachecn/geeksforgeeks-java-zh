# 在 Java 中将字符串列表转换为逗号分隔的字符串

> 原文:[https://www . geesforgeks . org/convert-a-list-of-string-to-a-逗号分隔字符串-in-java/](https://www.geeksforgeeks.org/convert-a-list-of-string-to-a-comma-separated-string-in-java/)

给定一个字符串列表，任务是在 Java 中将列表转换成逗号分隔的字符串。

**例:**

```java
Input: List<String> = ["Geeks", "ForGeeks", "GeeksForGeeks"]
Output: "Geeks, For, Geeks"

Input: List<String> = ["G", "e", "e", "k", "s"]
Output: "G, e, e, k, s"

```

**方法:**这可以通过如下字符串的 join()方法来实现。

1.  Get a list of strings.
2.  Use the join () method to form comma-separated strings from the list of strings by passing commas',' and the list as parameters.
3.  Print strings.

下面是上述方法的实现:

**程序:**

```java
// Java program to convert List of String
// to comma separated String

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Get the List of String
        List<String>
            list = new ArrayList<>(
                Arrays
                    .asList("Geeks",
                            "ForGeeks",
                            "GeeksForGeeks"));

        // Print the List of String
        System.out.println("List of String: " + list);

        // Convert the List of String to String
        String string = String.join(", ", list);

        // Print the comma separated String
        System.out.println("Comma separated String: "
                           + string);
    }
}
```