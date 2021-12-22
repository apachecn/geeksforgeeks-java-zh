# 在 Java 中将一组字符串转换为逗号分隔的字符串

> 原文:[https://www . geeksforgeeks . org/convert-a-set-string-to-a-逗号分隔字符串-in-java/](https://www.geeksforgeeks.org/convert-a-set-of-string-to-a-comma-separated-string-in-java/)

给定一组字符串，任务是在 Java 中将该组字符串转换为逗号分隔的字符串。

**例:**

```
Input: Set<String> = ["Geeks", "ForGeeks", "GeeksForGeeks"]
Output: "Geeks, For, Geeks"

Input: Set<String> = ["G", "e", "e", "k", "s"]
Output: "G, e, e, k, s"

```

**方法:**这可以通过如下字符串的 join()方法来实现。

1.  Take the string.
2.  Use the join () method to form comma-separated strings from the string set by passing commas',' and the string set as parameters.
3.  Print strings.

下面是上述方法的实现:

```
// Java program to convert Set of String
// to comma separated String

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Get the Set of String
        Set<String>
            set = new HashSet<>(
                Arrays
                    .asList("Geeks",
                            "ForGeeks",
                            "GeeksForGeeks"));

        // Print the Set of String
        System.out.println("Set of String: " + set);

        // Convert the Set of String to String
        String string = String.join(", ", set);

        // Print the comma separated String
        System.out.println("Comma separated String: "
                           + string);
    }
}
```

**输出:**

```
Set of String: [ForGeeks, Geeks, GeeksForGeeks]
Comma separated String: ForGeeks, Geeks, GeeksForGeeks

```