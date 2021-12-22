# 在 Java 中将字符串转换为字符列表

> 原文:[https://www . geesforgeks . org/convert-a-string-to-list-of-characters-in-Java/](https://www.geeksforgeeks.org/convert-a-string-to-a-list-of-characters-in-java/)

给定一个字符串，任务是将其转换为 Java 中的字符列表。

**示例:**

```java
Input: String = "Geeks"
Output: [G, e, e, k, s]

Input: String = "GeeksForGeeks"
Output: [G, e, e, k, s, F, o, r, G, e, e, k, s]

```

以下是各种方法:

1.  **Naive Method**

    **进场:**

    1.  获取字符串。
    2.  创建一个空的字符列表。
    3.  将字符串的每个字符添加到列表中。
    4.  返回列表。

    下面是上述方法的实现:

    ```java
    // Java program to illustrate
    // Converting a String to a List
    // of Characters
    import java.util.*;

    // Java program to convert
    // a String to a List of Characters

    class GFG {

        // Function to convert String
        // to List of Characters
        public static List<Character>
        convertStringToCharList(String str)
        {

            // Create an empty List of character
            List<Character> chars = new ArrayList<>();

            // For each character in the String
            // add it to the List
            for (char ch : str.toCharArray()) {

                chars.add(ch);
            }

            // return the List
            return chars;
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the String to be converted
            String str = "Geek";

            // Get the List of Character
            List<Character>
                chars = convertStringToCharList(str);

            // Print the list of characters
            System.out.println(chars);
        }
    }
    ```

    **Output:**

    ```java
    [G, e, e, k]

    ```

2.  **Using [Java 8 Stream:](https://www.geeksforgeeks.org/stream-in-java/)**

    **进场:**

    1.  获取字符串。
    2.  创建字符列表。
    3.  使用 chars()方法将字符串转换为 IntStream。
    4.  使用 mapToObj()方法将 IntStream 转换为 Stream <character>。</character>
    5.  使用 collect()
    6.  将元素收集为字符列表，并返回列表。

    下面是上述方法的实现:

    ```java
    // Java program to illustrate
    // Converting a String to a List
    // of Characters
    import java.util.*;
    import java.util.stream.Collectors;

    // Java program to convert
    // a String to a List of Characters

    class GFG {

        // Function to convert String
        // to List of Characters
        public static List<Character>
        convertStringToCharList(String str)
        {

          // Create an empty List of character
          List<Character> chars = str

          // Convert to String to IntStream
          .chars()

          // Convert IntStream to Stream<Character>
          .mapToObj(e -> (char)e)

          // Collect the elements as a List Of Characters
          .collect(Collectors.toList());

          // return the List
          return chars;
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the String to be converted
            String str = "Geek";

            // Get the List of Character
            List<Character>
                chars = convertStringToCharList(str);

            // Print the list of characters
            System.out.println(chars);
        }
    }
    ```

    **Output:**

    ```java
    [G, e, e, k]

    ```

3.  **Using Java 8 Stream:**

    **进场:**

    1.  获取字符串。
    2.  使用抽象列表接口将字符串转换为字符列表
    3.  返回列表。

    下面是上述方法的实现:

    ```java
    import java.util.*;

    // Java program to convert
    // a String to a List of Characters

    class GFG {

        // Function to convert String
        // to List of Characters
        public static List<Character>
        convertStringToCharList(String str)
        {
            return new AbstractList<Character>() {

                @Override
                public Character get(int index)
                {
                    return str.charAt(index);
                }

                @Override
                public int size()
                {
                    return str.length();
                }
            };
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the String to be converted
            String str = "Geek";

            // Get the List of Character
            List<Character>
                chars = convertStringToCharList(str);

            // Print the list of characters
            System.out.println(chars);
        }
    }
    ```

    **Output:**

    ```java
    [G, e, e, k]

    ```