# 如何在 Java 中填充字符串

> 原文:[https://www.geeksforgeeks.org/how-to-pad-a-string-in-java/](https://www.geeksforgeeks.org/how-to-pad-a-string-in-java/)

给定一个特定长度的字符串 **str** ，任务是用给定的字符 **ch** 填充这个字符串，以使这个字符串的长度为 **L** 。

**注意:**填充必须以所有三种格式完成:左填充、右填充和中心填充。

**示例:**

> **输入:**str = " geesforgeks "，ch ='-'，L = 20
> **输出:**
> 左填充:——geesforgeks
> 中心填充:——geesforgeks——
> 右填充:geesforgeks—————
> 
> **输入:** str = "GfG "，ch ='# '，L = 5
> **输出:**
> 左填充:##GfG
> 中心填充:#GfG#
> 右填充:GfG##

垫一根[弦](https://www.geeksforgeeks.org/strings-in-java/)的方法有很多:

1.  **Using [String format()](https://www.geeksforgeeks.org/java-string-format-examples/) method:** This method is used to return a formatted string using the given locale, specified format string and arguments.

    **注意:这个方法只能做左右填充。**

    **进场:**

    *   获取填充所在的字符串。
    *   使用 [String.format()方法](https://www.geeksforgeeks.org/java-string-format-examples/)在字符串的左右两边填充空格，然后使用 [String.replace()方法](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/)将这些空格替换为给定的字符。
    *   对于左填充，使用 String.format()方法的语法是:

        ```java
        String.format("%[L]s", str).replace(' ', ch);

        ```

    *   对于右填充，使用 String.format()方法的语法是:

        ```java
        String.format("%-[L]s", str).replace(' ', ch);

        ```

    *   如果*长度“L”*小于字符串的初始长度，则相同的字符串不变地返回。

    下面是上述方法的实现:

    **示例:**

    ```java
    // Java implementation to pad a String

    import java.lang.*;
    import java.io.*;

    public class GFG {

        // Function to perform left padding
        public static String
        leftPadding(String input, char ch, int L)
        {

            String result
                = String

                      // First left pad the string
                      // with space up to length L
                      .format("%" + L + "s", input)

                      // Then replace all the spaces
                      // with the given character ch
                      .replace(' ', ch);

            // Return the resultant string
            return result;
        }

        // Function to perform right padding
        public static String
        rightPadding(String input, char ch, int L)
        {

            String result
                = String

                      // First right pad the string
                      // with space up to length L
                      .format("%" + (-L) + "s", input)

                      // Then replace all the spaces
                      // with the given character ch
                      .replace(' ', ch);

            // Return the resultant string
            return result;
        }

        // Driver code
        public static void main(String[] args)
        {

            String str = "GeeksForGeeks";
            char ch = '-';
            int L = 20;

            System.out.println(
                leftPadding(str, ch, L));
            System.out.println(
                rightPadding(str, ch, L));
        }
    }
    ```

    **Output:**

    ```java
    -------GeeksForGeeks
    GeeksForGeeks-------

    ```

2.  **Using [Apache Common Lang](http://commons.apache.org/lang/):** Apache Commons Lang package provides the **StringUtils** class, which contains the **leftPad(), center() and rightPad()** method to easily left pad, center pad and right pad a String respectively.

    **注意:**该模块必须在运行代码之前安装。因此，这些代码不会在在线编译器上运行。

    **进场:**

    *   获取填充所在的字符串。
    *   对于左填充，使用**stringtutils . left pad()**方法的语法是:

        ```java
        StringUtils.leftPad(str, L, ch);

        ```

    *   对于中心填充，使用 **StringUtils.center()** 方法的语法是:

        ```java
        StringUtils.center(str, L, ch);

        ```

    *   对于右填充，使用 **StringUtils.rightPad()** 方法的语法是:

        ```java
        StringUtils.rightPad(str, L, ch);

        ```

    *   如果*长度“L”*小于字符串的初始长度，则相同的字符串不变地返回。

    下面是上述方法的实现:

    **示例:**

    ```java
    // Java implementation to pad a String

    import java.lang.*;
    import java.io.*;

    public class GFG {

        // Function to perform left padding
        public static String
        leftPadding(String input, char ch, int L)
        {

            // Left pad the string
            String result
                = StringUtils.leftPad(str, L, ch);

            // Return the resultant string
            return result;
        }

        // Function to perform center padding
        public static String
        centerPadding(String input, char ch, int L)
        {

            // Center pad the string
            String result
                = StringUtils.center(str, L, ch);

            // Return the resultant string
            return result;
        }

        // Function to perform right padding
        public static String
        rightPadding(String input, char ch, int L)
        {

            // Right pad the string
            String result
                = StringUtils.rightPad(str, L, ch);

            // Return the resultant string
            return result;
        }

        // Driver code
        public static void main(String[] args)
        {

            String str = "GeeksForGeeks";
            char ch = '-';
            int L = 20;

            System.out.println(
                leftPadding(str, ch, L));
            System.out.println(
                centerPadding(str, ch, L));
            System.out.println(
                rightPadding(str, ch, L));
        }
    }
    ```

    **Output:**

    ```java
    -------GeeksForGeeks
    ---GeeksForGeeks----
    GeeksForGeeks-------

    ```