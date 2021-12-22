# 在 Java 中将字符串转换为逗号分隔列表

> 原文:[https://www . geesforgeks . org/convert-string-to-逗号分隔列表-in-java/](https://www.geeksforgeeks.org/convert-string-into-comma-separated-list-in-java/)

给定一个字符串，任务是将其转换为逗号分隔的列表。

**示例:**

```java
Input: String = "Geeks For Geeks"
Output: List = [Geeks, For, Geeks]

Input: String = "G e e k s"
Output: List = [G, e, e, k, s]

```

**方法:**这可以通过将字符串转换为字符串数组，然后从该数组创建一个列表来实现。然而，根据创建方法，该列表可以分为两种类型——可修改的和不可修改的。

*   **创建不可修改列表** :

    ```java
    // Java program to convert String
    // to comma separated List

    import java.util.*;

    public class GFG {
        public static void main(String args[])
        {

            // Get the String
            String string = "Geeks For Geeks";

            // Print the String
            System.out.println("String: " + string);

            // convert String to array of String
            String[] elements = string.split(" ");

            // Convert String array to List of String
            // This List is unmodifiable
            List<String> list = Arrays.asList(elements);

            // Print the comma separated List
            System.out.println("Comma separated List: "
                               + list);
        }
    }
    ```

    **输出:**

    ```java
    String: Geeks For Geeks
    Comma separated List: [Geeks, For, Geeks]

    ```

*   **创建可修改列表** :

    ```java
    // Java program to convert String
    // to comma separated List

    import java.util.*;

    public class GFG {
        public static void main(String args[])
        {

            // Get the String
            String string = "Geeks For Geeks";

            // Print the String
            System.out.println("String: " + string);

            // convert String to array of String
            String[] elements = string.split(" ");

            // Convert String array to List of String
            // This List is modifiable
            List<String>
                list = new ArrayList<String>(
                    Arrays.asList(elements));

            // Print the comma separated List
            System.out.println("Comma separated List: "
                               + list);
        }
    }
    ```

    **输出:**

    ```java
    String: Geeks For Geeks
    Comma separated List: [Geeks, For, Geeks]

    ```