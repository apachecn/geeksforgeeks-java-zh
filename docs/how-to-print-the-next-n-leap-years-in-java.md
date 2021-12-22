# 如何用 Java 打印下 N 个闰年？

> 原文:[https://www . geesforgeks . org/如何在 java 中打印下一个 n-leap-years/](https://www.geeksforgeeks.org/how-to-print-the-next-n-leap-years-in-java/)

**概念:**闰年解题的基本主张是间隔 4 年，这本身就是错误的。日历中的任意一年要想成为闰年，它必须满足以下条件。现在，如果一年是闰年，目标只是简单地在一个日历年中打印连续的相同种类的年份，即所有年份都应该在闰年之前，或者坚持考虑闰年来说明和实现相同。

**方法:**解决问题很简单，分成两半。前半部分是计算闰年和为闰年编写代码的重点。后半部分只是强调每当遇到闰年时保持计数，并与前半部分同步。

一年必须满足的条件称为闰年

*   The year should be a multiple of 400.
*   The year should be a multiple of 4, not a multiple of 100.

**算法:**

1.  条件检查 4 的可除性-如果数字可被 4 整除，检查将进一步进行，如果数字不能被 4 整除，那么肯定不是闰年。
2.  条件检查 100 的可除性-这里得到的年已经可以被 4 整除。现在，如果该年满足上述条件，那么如果该年可被 100 整除，则该年继续进行进一步的条件检查。如果这个数不能被 100 整除，那么肯定不是闰年。
3.  用 400 检查可除性的条件-这里得到的年份已经可以被 4 和 100 整除。现在再进一步，如果年能被 400 整除，那么肯定是闰年，否则肯定不是闰年。
4.  到目前为止，这里获得的年份是闰年，打印闰年的方法非常简单
    *   用零初始化一个变量以保持圈年计数
    *   当确定该年是闰年时，递增计数
    *   迭代考虑条件语句的计数，如果条件失败，只需返回以前满足条件的所有年份。

**插图:**

```java
Input 1: year = 2020, N = 15
Output: 2024
       2028
       2032
       2036
       2040
       2044
       2048
       2052
       2056
       2060
       2064
       2068
       2072
       2076
       2080

Input 2: year = 2022, N = 2
Output:    2024
           2028
```

**实现:**下面是用 Java 举例说明上面的插图:

T5】JavaT7

```java
// Java program to print the next n leap years

// Importing generic Classes/Files
import java.io.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Considering current year & initializing same
        int year = 2020;
        // Considering user entered custom leap year

        int n = 15;
        // n is the no of leap years after year 2020
        // that is needed to print

        int count = 0;
        // Creating and initializing a variable
        // to maintain count of leap years

        while (count != n)
        // Conditionality check- Count variable should never
        // equals number of leap years to be printed
        {

            year = year + 1;
            // Incrementing the year count by 1

            if ((year % 400 == 0)
                || (year % 4 == 0 && year % 100 != 0)) {

                // If the year is leap year,then increment
                // the count
                count++;

                // Print the leap year
                System.out.println(year);
            }
        }
    }
}
```

T8T10**输出**T1