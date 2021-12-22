# 提取给定年份最后两位数字的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序提取-给定年份的最后两位数/](https://www.geeksforgeeks.org/java-program-to-extract-last-two-digits-of-a-given-year/)

顾名思义，在需要执行操作来处理数字的地方，模运算符起着至关重要的作用。这里的目标是提取一个数字的最后几个数字。因此，使问题更容易思考，如果目标是从一个数字中提取最后一个数字，该怎么办。在这种情况下，数字代表年份。提取最后一位所涉及的数学概念是将给定的数字除以一个数，使得余数应该与最后一位数字的余数相同。为了提取最后一位数字，给定数字必须除以的数字必须是 10。

> 模用“%”表示，用来求余数

**示例:**从数字中提取最后一位数字

```
Random Number = 1997
Last Digit       = 7
Goal: 1997 % (x) = 7            // Goal is Divide 1997 by x such that remainder is 7
         if x = 10           // 1997 % 10 = 7 that is the last digit    

```

现在，为了提取最后两位数字，我们将使用相同的方法处理数字，只是根据数学单位标准，给定的数字将以 100 为模。

示例:从数字中提取最后两位数字

```
Input  : year = 2020
Output : 20

Input  : year = 1983
Output : 83

Input  : year = 2000
Output : 00

```

**我们可以用两种不同的方法来实现:**

*   使用[模算术运算符](https://www.geeksforgeeks.org/operators-in-java/#Arithmetic%20Operators)
*   使用[字符串子串()方法](https://www.geeksforgeeks.org/substring-in-java/)

**A .使用** [**模算术运算符**](https://www.geeksforgeeks.org/operators-in-java/#Arithmetic%20Operators) **:** 我们可以使用模运算符(%)通过取年份的模 100 来提取最后两位数字。

数学单位制的内部运作

```
Let us consider 1983, we can write it as 
1983 = 1*1000 + 9*100 + 8*10 + 3
So when we take modulo by 100, we will just have the last two digits as remainder.
1983 % 100 = 1*1000 % 100 + 9*100 % 100 + 8*10 % 100 + 3 % 100 = 0 + 0 + 8*10 + 3 = 83
```

下面描述上述方法的实现

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to extract last two digits of a year

// Importing Classes/Files
import java.util.*;

public class GFG {

    // Main Driver Code
    public static void main(String args[])
    {
        // Initializing year as String
        int year = 1983;

        // Printing last two digits of a number
        // by modulo with 100
        System.out.print(year % 100);
    }
}
```

**Output**

```
83
```

**B .使用** [**String substring()方法**](https://www.geeksforgeeks.org/substring-in-java/) **:** 该方法返回一个新的字符串，该字符串是给定字符串的子字符串。因此，要提取最后两位数字，我们需要获取索引 2 之后的子字符串。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to extract last two digits of a year
public class GFG {

    // Function to extract last to digits of a year
    static int extractLastTwo(String year)
    {
        // using substring() to extract the last two digit
        // as substring
        String lastTwoDigits = year.substring(2);

        return Integer.parseInt(
            lastTwoDigits); // Returning last two digits as
                            // an integer
    }

    public static void main(String args[])
    {
        // Initializing year as String
        String year = "1983";

        System.out.print(extractLastTwo(year));
    }
}
```

**Output**

```
83
```