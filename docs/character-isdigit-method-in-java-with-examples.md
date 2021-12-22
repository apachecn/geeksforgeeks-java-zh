# Java 中的 Character isDigit()方法，带示例

> 原文:[https://www . geesforgeks . org/character-is digit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-isdigit-method-in-java-with-examples/)

1.  The **java.lang.Character.isDigit(char ch)** is an inbuilt method in java which determines whether a specified character is a digit or not. There are few conditions that a character must accomplish to be accepted as a digit. That is if the general category type of a character, provided by Character.getType(ch), is DECIMAL_DIGIT_NUMBER, then the character is a digit.
    Some Unicode character ranges that contain digits:

    > 从' \u0030 '到' \u0039' : ISO-LATIN-1 数字(' 0 '到' 9')
    > 从' \u0660 '到' \u0669 ':阿拉伯-印度数字
    > 从' \u06F0 '到' \u06F9 ':扩展阿拉伯-印度数字
    > 从' \u0966 '到' \u096F ':梵文数字
    > 从' \uFF10 '到' \uFF19 ':全幅

    除了上述范围，许多其他字符范围也包含数字。

    **语法:**

    ```java
    public static boolean isDigit(char ch)

    ```

    **参数:**该方法接受字符参数 **ch** 作为自变量，待测试。

    **返回值:**这个方法返回一个布尔值。如果 **ch** 是数字，则返回 *True* ，否则返回 *False。*

    **注意:**此方法无法处理[补充字符](https://docs.oracle.com/javase/8/docs/api/java/lang/Character.html#supplementary)。若要支持所有 Unicode 字符，包括补充字符，请使用 isDigit(int)方法。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java program to illustrate the
    // Character.isDigit() method

    import java.util.*;
    import java.lang.*;

    public class GFG {

        public static void main(String[] args)
        {

            // two characters
            char c1 = 'A', c2 = '4';

            // Function to check if the character
            // is digit or not
            System.out.println(
                c1 + " is a digit -> "
                + Character.isDigit(c1));
            System.out.println(
                c2 + " is a digit -> "
                + Character.isDigit(c2));
        }
    }
    ```

    **Output:**

    ```java
    A is a digit -> false
    4 is a digit -> true

    ```

    **程序 2:**

    ```java
    // Java program to illustrate the
    // Character.isDigit() method

    import java.util.*;
    import java.lang.*;

    public class GFG {

        public static int search_digit(String s)
        {

            // Function to check if is digit
            // is found or not
            for (int i = 0; i < s.length(); i++) {
                if (Character.isDigit(
                        s.charAt(i))
                    == true) {
                    // return position of digit
                    return i + 1;
                }
            }
            // return 0 if digit not present
            return 0;
        }

        public static void main(String[] args)
        {

            // Array of strings
            String[] arr = { "ABC4DEF", "QWERTY" };

            // To store the position of digit
            int index = 0;

            // Traverse the array arr[] to find digit
            // within it's elements
            for (String x : arr) {
                index = search_digit(x);
                if (index != 0) {
                    System.out.println(
                        "Digit found at : "
                        + (index)
                        + "th position.");
                }
                else {
                    System.out.println(
                        "Digit not present.");
                }
            }
        }
    }
    ```

    **Output:**

    ```java
    Digit found at : 4th position.
    Digit not present.

    ```

2.  **java . lang . character . IsDigit(int CodePoint)**是 Java 中的一个内置方法，用于确定指定的整数类型的 Unicode 代码点字符是否为数字。
    一个字符要被接受为一个数字，几乎没有必须满足的条件。也就是说，如果由 getType(codepoint)提供的字符的一般类别类型是 DECIMAL_DIGIT_NUMBER，那么该字符就是一个数字。一些包含数字的 Unicode 字符范围:

> 从' \u0030 '到' \u0039' : ISO-LATIN-1 数字(' 0 '到' 9')
> 从' \u0660 '到' \u0669 ':阿拉伯-印度数字
> 从' \u06F0 '到' \u06F9 ':扩展阿拉伯-印度数字
> 从' \u0966 '到' \u096F ':梵文数字
> 从' \uFF10 '到' \uFF19 ':全幅

除了上述范围，许多其他字符范围也包含数字。

**语法:**

```java
public static boolean isDigit(int codePoint)

```

**参数:**该方法接受整数类型的 unicode 字符参数**码点**作为参数，待测试。

**返回值:**这个方法返回一个布尔值。如果指定的字符是数字，则返回*真*，否则返回*假。*

以下程序说明了上述方法:
**程序 1:**

```java
// This program demonstrates the use of
// isDigit(int codePoint) method of Character class.
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create codePoints
        int cp1 = 57;
        int cp2 = 84;

        // Check whether the codePoints
        // are digit or not.
        System.out.println(
            "The codePoint cp1 is a digit -> "
            + Character.isDigit(cp1));
        System.out.println(
            "The codePoint cp2 is a digit -> "
            + Character.isDigit(cp2));
    }
}
```

**Output:**

```java
The codePoint cp1 is a digit -> true
The codePoint cp2 is a digit -> false

```

**程序 2:**

```java
// This program demonstrates the use of
// isDigit(int codePoint) method of
// Character class.
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        // create codePoints
        int cp1 = 0x50;
        int cp2 = 0x06f8;

        // Check whether the codePoints
        // are digit or not.
        System.out.println(
            "The codePoint cp1 is a digit -> "
            + Character.isDigit(cp1));
        System.out.println(
            "The codePoint cp2 is a digit -> "
            + Character.isDigit(cp2));
    }
}
```

**Output:**

```java
The codePoint cp1 is a digit -> false
The codePoint cp2 is a digit -> true

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/character . html # isDigit-char-](https://docs.oracle.com/javase/8/docs/api/java/lang/Character.html#isDigit-char-)