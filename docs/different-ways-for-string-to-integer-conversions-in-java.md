# Java 中字符串到整数转换的不同方式

> 原文:[https://www . geesforgeks . org/Java 中字符串到整数转换的不同方式/](https://www.geeksforgeeks.org/different-ways-for-string-to-integer-conversions-in-java/)

在 [Java](https://www.geeksforgeeks.org/java-tutorials/) 中给定一个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)，任务是将这个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)转换成[整数](https://www.geeksforgeeks.org/java-lang-integer-class-java/)。

**示例:**

```java
Input: str = "1234"
Output: 1234

Input: str = "456"
Output: 456

```

1.  **Convert using [Integer.parseInt(String)](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/)**
    The Integer class has a static method that returns an integer object representing the specified String parameter.
    **Syntax :**

    ```java
    public static int parseInt(String str) throws NumberFormatException
    or
    public static int parseInt(String str, int radix) throws NumberFormatException

    ```

    **参数:**

    *   **字符串**:需要转换为整数的字符串。它还可以将第一个字符作为减号'-' ('\u002D ')或加号'+' ('\u002B ')来表示数字的符号。
    *   **基数**:解析字符串时使用的基数。此参数仅特定于该方法的第二个变体。

    **异常:****numberformateexception**如果出现以下任一情况，此方法将引发:

    对于这两种变体:

    *   字符串为空或长度为零
    *   字符串表示的值不是 int 类型的值
    *   特别是对于函数的 parseInt(字符串，整数基数)变体:
        *   第二个参数基数要么小于[字符。最小基数](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#MIN_RADIX)或大于[字符。最大基数](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#MAX_RADIX)
        *   字符串的任何字符都不是指定基数的数字，除了第一个字符可以是减号'-' ('\u002D ')或加号'+' ('\u002B ')，前提是字符串长度大于 1

    **示例:**

    ```java
    class GfG {
        public static void main(String args[])
        {
            String str = "1234";

            int num1 = Integer.parseInt(str);
            System.out.println("Integer using "
                               + "first variant of"
                               + " praseInt = "
                               + num1);

            int num2 = Integer.parseInt(str, 16);
            System.out.println("Integer using "
                               + "second (radix) variant"
                               + " of praseInt = "
                               + num2);
        }
    }
    ```

    **Output:**

    ```java
    Integer using first variant of praseInt = 1234
    Integer using second (radix) variant of praseInt = 4660

    ```

2.  **Convert using [Integer.valueOf(String)](https://www.geeksforgeeks.org/integer-valueof-method-in-java/)**

    **语法:**

    ```java
    public static Integer valueOf(String str)

    ```

    **参数:**该方法接受待解析的字符串类型的单参数**字符串**。

    **返回值:**该方法返回一个 **[整数](https://www.geeksforgeeks.org/java-lang-integer-class-java/)** 对象，该对象保存由字符串参数表示的值。

    **示例:**

    ```java
    class GfG {
        public static void main(String args[])
        {
            String str = "1234";

            int num1 = Integer.valueOf(str);
            System.out.println("Integer using"
                               + " valueOf() = "
                               + num1);
        }
    }
    ```

    **Output:**

    ```java
    Integer using valueOf() = 1234

    ```