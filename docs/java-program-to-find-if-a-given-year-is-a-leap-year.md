# Java 程序查找给定年份是否是闰年

> 原文:[https://www . geeksforgeeks . org/Java-如果给定年份是闰年，则程序查找/](https://www.geeksforgeeks.org/java-program-to-find-if-a-given-year-is-a-leap-year/)

闰年包含 366 天，每四年一次。每个闰年都对应这些事实:

*   百年是以 00 结尾的一年。一个百年只有被 400 整除才是闰年。
*   如果闰年能被 4 整除，它就能被识别出来。
*   一个世纪的年份应该同时被 4 和 100 整除。
*   非百年年份应该只能被 4 整除。

让我们来看看一年是否是闰年。

**不使用扫描仪类**

顾名思义，用户肯定不会选择自己喜欢的年份。以下程序说明了确定一年是否为闰年的方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find a leap year

// Importing Classes/Files
import java.io.*;

// Class for leap-year dealing
public class GeeksforGeeks {

    // Method to check leap year
    public static void isLeapYear(int year)
    {
        // flag to take a non-leap year by default
        boolean is_leap_year = false;

        // If year is divisible by 4
        if (year % 4 == 0) {

            // To identify whether it
            // is a century year or
            // not
            if (year % 100 == 0) {

                // Checking if year is divisible by 400
                // therefore century leap year
                if (year % 400 == 0) {
                    is_leap_year = true;
                }

                else {
                    is_leap_year = false;
                }
            }

            // Out of if loop that is Non century year
            // but divisible by 4, therefore leap year
            is_leap_year = true;
        }

        // We land here when corresponding if fails
        // If year is not divisible by 4
        else

            // Flag dealing-  Non leap-year
            is_leap_year = false;

        if (!is_leap_year) {
            System.out.println(year + " : Non Leap-year");
        }

        else {
            System.out.println(year + " : Leap-year");
        }
    }

    // Main Driver Code
    public static void main(String[] args)
    {
        // Calling our function by
        // passing century year
        isLeapYear(2000);

        // Calling our function by
        // passing Non-century year
        isLeapYear(2002);
    }
}
```

**输出:**

```java
2000 : Leap-year
2002 : Non Leap-year
```

2000 年是可被 100 和 4 整除的百年。2002 年不能被 4 整除，因此不是闰年。

**使用扫描仪等级**

在这里，用户可以灵活地输入自己选择的年份，因为扫描仪类是在这里导入的，其余的 if-else 块也合并在一个语句中，以检查输入的年份是否是闰年。以下程序说明了确定一年是否为闰年的方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to check Leap-year
// by taking input from user

// Importing Classes/Files
import java.io.*;

// Importing Scanner Class
import java.util.Scanner;

// Class to check leap-year or not
public class GFG {

    // Driver Main code
    public static void main(String[] args)
    {
        // Considering any random year
        int year;

        // Taking input from user using Scanner Class
        // scn is an object made of Scanner Class
        Scanner scn = new Scanner(System.in);
        year = scn.nextInt();

        // 1st condition check- It is century leap year
        // 2nd condition check- It is leap year and not
        // century year
        if ((year % 400 == 0)
            || ((year % 4 == 0) && (year % 100 != 0))) {

            // Both conditions true- Print leap year
            System.out.println(year + " : Leap Year");
        }

        else {
            // Any condition fails- Print Non-leap year
            System.out.println(year + " : Non - Leap Year");
        }
    }
}
```

**输入:**

```java
2012
```

**输出:**

```java
2012 : Leap Year
```