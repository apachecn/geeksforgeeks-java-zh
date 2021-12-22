# 从字符串中获取字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-a-character-from-string/](https://www.geeksforgeeks.org/java-program-to-get-a-character-from-a-string/)

给定一个字符串，任务是在特定的索引处从该字符串中获取特定的字符。

**示例:**

```java
Input: str = "Geeks", index = 2
Output: e

Input: str = "GeeksForGeeks", index = 5
Output: F

```

以下是各种方法:

*   **Using String.charAt() method**:
    1.  获取字符串和索引
    2.  使用 String.charAt(index)方法获取特定字符。
    3.  返回特定字符。

    下面是上述方法的实现:

    ```java
    // Java program to get a specific character
    // from a given String at a specific index

    class GFG {

        // Function to get the specific character
        public static char
        getCharFromString(String str, int index)
        {
            return str.charAt(index);
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the String
            String str = "GeeksForGeeks";

            // Get the index
            int index = 5;

            // Get the specific character
            char ch = getCharFromString(str, index);

            System.out.println("Character from " + str
                               + " at index " + index
                               + " is " + ch);
        }
    }
    ```

    **Output:**

    ```java
    Character from GeeksForGeeks at index 5 is F

    ```

*   **Using String.toCharArray() method**:
    1.  获取字符串和索引
    2.  使用 String.toCharArray()方法将字符串转换为字符数组。
    3.  获取字符数组特定索引处的特定字符。
    4.  返回特定字符。

    下面是上述方法的实现:

    ```java
    // Java program to get a specific character
    // from a given String at a specific index

    class GFG {

        // Function to get the specific character
        public static char
        getCharFromString(String str, int index)
        {
            return str.toCharArray()[index];
        }

        // Driver code
        public static void main(String[] args)
        {
            // Get the String
            String str = "GeeksForGeeks";

            // Get the index
            int index = 5;

            // Get the specific character
            char ch = getCharFromString(str, index);

            System.out.println("Character from " + str
                               + " at index " + index
                               + " is " + ch);
        }
    }
    ```

    **Output:**

    ```java
    Character from GeeksForGeeks at index 5 is F

    ```

*   **Using Java 8 Streams**:
    1.  获取字符串和索引
    2.  使用 String.chars()方法将字符串转换为 IntStream。
    3.  使用 IntStream.mapToObj()方法将 IntStream 转换为 Stream <character>。</character>
    4.  使用 toArray()方法将流<character>转换为字符【】。</character>
    5.  从这个字符数组中获取特定索引处的元素。
    6.  返回具体人物。

    下面是上述方法的实现:

    ```java
    // Java program to get a specific character
    // from a given String at a specific index

    class GFG {

        // Function to get the specific character
        public static char
        getCharFromString(String str, int index)
        {
            return str
                // Convert String into IntStream
                .chars()

                // Convert IntStream into Stream<Character>
                .mapToObj(ch -> (char)ch)

                // Convert Stream<Character> into Character[]
                // and get the element at the specific index
                .toArray(Character[] ::new)[index];
        }

        // Driver code
        public static void main(String[] args)
        {
            // Get the String
            String str = "GeeksForGeeks";

            // Get the index
            int index = 5;

            // Get the specific character
            char ch = getCharFromString(str, index);

            System.out.println("Character from " + str
                               + " at index " + index
                               + " is " + ch);
        }
    }
    ```

    **Output:**

    ```java
    Character from GeeksForGeeks at index 5 is F

    ```

*   **Using String.codePointAt() method**:
    1.  获取字符串和索引
    2.  使用 String.codePointAt()方法获取特定索引处的特定字符 ASCII 值。
    3.  使用类型转换将该 ASCII 值转换为字符。
    4.  返回特定字符。

    下面是上述方法的实现:

    ```java
    // Java program to get a specific character
    // from a given String at a specific index

    class GFG {

        // Function to get the specific character
        public static char
        getCharFromString(String str, int index)
        {
            return (char)str.codePointAt(index);
        }

        // Driver code
        public static void main(String[] args)
        {
            // Get the String
            String str = "GeeksForGeeks";

            // Get the index
            int index = 5;

            // Get the specific character
            char ch = getCharFromString(str, index);

            System.out.println("Character from " + str
                               + " at index " + index
                               + " is " + ch);
        }
    }
    ```

    **Output:**

    ```java
    Character from GeeksForGeeks at index 5 is F

    ```

*   **Using String.getChars() method**:
    1.  获取字符串和索引
    2.  创建一个大小为 1 的空字符数组
    3.  使用 String.getChars()方法将字符串中特定索引处的元素复制到 char[]中。
    4.  获取字符数组索引 0 处的特定字符。
    5.  返回特定字符。

    下面是上述方法的实现:

    ```java
    // Java program to get a specific character
    // from a given String at a specific index

    class GFG {

        // Function to get the specific character
        public static char
        getCharFromString(String str, int index)
        {
            // Create a character array of size 1
            char[] singleCharArray = new char[1];

            // Get the specific character from the String
            // into the char[] at index 0
            str.getChars(index, index + 1, singleCharArray, 0);

            // Return the specific character
            // present at index 0 in char[]
            return singleCharArray[0];
        }

        // Driver code
        public static void main(String[] args)
        {
            // Get the String
            String str = "GeeksForGeeks";

            // Get the index
            int index = 5;

            // Get the specific character
            char ch = getCharFromString(str, index);

            System.out.println("Character from " + str
                               + " at index " + index
                               + " is " + ch);
        }
    }
    ```

    **Output:**

    ```java
    Character from GeeksForGeeks at index 5 is F

    ```