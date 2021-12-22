# 检查字符串是否包含特殊字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查字符串是否由特殊字符组成/](https://www.geeksforgeeks.org/java-program-to-check-whether-the-string-consists-of-special-characters/)

特殊字符是那些既不是字母也不是数字的字符。空白也不被认为是特殊字符。特殊字符的例子有:-！(感叹号)、、(逗号)、#(哈希)等。

**方法:**

1.  [使用字符类](https://www.geeksforgeeks.org/character-class-java/#:~:text=Syntax%20%3A%20char%20toLowerCase(char%20ch,of%20the%20specified%20char%20value.&text=toString(char%20ch)%20%3A%20It,we%20cannot%20pass%20ASCII%20value.)
2.  [使用正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)

**方法 1:** 使用字符类

方法如下:

1.  遍历字符串的所有字符。
2.  同时，我们将使用 java [字符类](https://www.geeksforgeeks.org/character-class-java/#:~:text=Syntax%20%3A%20char%20toLowerCase(char%20ch,of%20the%20specified%20char%20value.&text=toString(char%20ch)%20%3A%20It,we%20cannot%20pass%20ASCII%20value.)检查每个字符是字母、数字还是空白。
3.  它被发现没有上述的特殊字符的标志。
4.  并行地，我们将维护一个特殊字符计数的计数器。
5.  最后，根据需要打印和显示所需的计数或特殊字符。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check Whether String contains Special
// Characters Using Character Class

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing count for
        // special characters
        int count = 0;

        // Input custom string
        String s
            = "!#$GeeeksforGeeks.Computer.Science.Portal!!";

        // Iterating through the string
        // using standard length() method
        for (int i = 0; i < s.length(); i++) {

            // Checking the character for not being a
            // letter,digit or space
            if (!Character.isDigit(s.charAt(i))
                && !Character.isLetter(s.charAt(i))
                && !Character.isWhitespace(s.charAt(i))) {
                // Incrementing the countr for spl
                // characters by unity
                count++;
            }
        }

        // When there is no special character encounterd
        if (count == 0)

            // Display the print statement
            System.out.println(
                "No Special Characters found.");
        else

            // Special sharacter/s found then
            // Display the print statement
            System.out.println(
                "String has Special Characters\n" + count + " "
                + "Special Characters found.");
    }
}
```

**Output**

```
String has Special Characters
8 Special Characters found.
```

**方法 2:** 使用正则表达式

1.  创建一个不匹配任何字母、数字或空白的[正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)。
2.  我们将根据正则表达式使用 Matcher 类作为我们的输入字符串。
3.  现在，如果正则表达式中存在任何“字符匹配”，则字符串包含特殊字符，否则它不包含任何特殊字符。
4.  打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check Whether String contains Special
// Characters using Regex classes

// Importing regex classes from java.util package to
// match a specific patteren
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing strings randomly
        // with input characters

        // Custom Input as String 1
        String s1 = "GeeksForGeeks";

        // Creating regex pattern by
        // creating object of Pattern class
        Pattern p = Pattern.compile(
            "[^a-z0-9 ]", Pattern.CASE_INSENSITIVE);

        // Creating matcher for above pattern on our string
        Matcher m = p.matcher(s1);

        // Now finding the matches for which
        // let us set a boolean flag and
        // imposing find() method
        boolean res = m.find();

        // Output will be based on boolean flag

        // If special characters are found
        if (res)

            // Display this message on the console
            System.out.println(
                "String1 contains Special Characters");

        // If we reach here means no special characters are
        // found
        else

            // Display this message on the console
            System.out.println(
                "No Special Characters found in String 1");

        // Custom Input as String 2
        String s2 = "!!Geeks.For.Geeks##";

        // Creating matcher for above pattern on our string
        // by creating object of matcher class
        Matcher m2 = p.matcher(s2);

        // Finding the matches using find() method
        boolean res2 = m2.find();

        // If matches boolean returns true
        if (res2)

            // Then print and display thta special
            // characters are found
            System.out.println(
                "String 2 contains Special Characters");

        // If not
        else

            // Then Display the print statement below
            System.out.println(
                "No Special Characters found in String 2");
    }
}
```

**Output**

```
No Special Characters found in String 1
String 2 contains Special Characters
```