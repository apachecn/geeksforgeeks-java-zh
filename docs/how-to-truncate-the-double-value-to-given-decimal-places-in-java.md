# 如何在 Java 中将双精度值截断到给定的小数位数？

> 原文:[https://www . geesforgeks . org/如何截断 java 中给定小数位数的双精度值/](https://www.geeksforgeeks.org/how-to-truncate-the-double-value-to-given-decimal-places-in-java/)

最简单地说，截断**是指**将一个**数**的小数部分截断。一种近似十进制数的方法，通过去掉某一点后的所有小数位而不取整。

给定一个双精度值和一个小数位，将该值截断到给定的小数点。

**示例:**

```java
Input: val = 3.142857142857143
Decimal point = 3
Output =  3.142

Upto 3 decimal places
```

**方法 1:数学上使用**:

*   通过乘以 10^n 将给定值的小数移动到给定的小数点
*   请数字代表发言，用数字除以 10^n
*   最终值是截断值

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to truncate the double value to
// a particular decimal point

import java.io.*;

class GFG {

    static void change(double value, int decimalpoint)
    {

        // Using the pow() method
        value = value * Math.pow(10, decimalpoint);
        value = Math.floor(value);
        value = value / Math.pow(10, decimalpoint);

        System.out.println(value);

        return;
    }

      // Main Method
    public static void main(String[] args)
    {

        double firstvalue = 1212.12131131;
        int decimalpoint = 4;

        change(firstvalue, decimalpoint);

        double secondvalue = 3.142857142857143;
        int decimalpoint2 = 3;

        change(secondvalue, decimalpoint2);
    }
}
```

**Output**

```java
1212.1213
3.142
```

**方法 2:使用字符串匹配方法**

*   将数字转换为字符串
*   当“”时，启动计数器变量在字符串中找到
*   将计数器增加到小数点
*   存储新字符串并以双精度格式解析它

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to truncate the double
// value using string matching

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        double firstvalue = 1212.12131131;

        // decimal point
        int decimalpoint = 6;

        // convert the double value in string
        String temp_value = "" + firstvalue;
        String string_value = "";

        int counter = -1;

        for (int i = 0; i < temp_value.length(); ++i) {

            // checking the condition
            if (counter > decimalpoint) {
                break;
            }
            else

                if (temp_value.charAt(i) == '.') {
                counter = 1;
            }
            else if (counter >= 1) {

                ++counter;
            }

            // converting the number into string
            string_value += temp_value.charAt(i);
        }

        // parse the string
        double new_value = Double.parseDouble(string_value);

        System.out.println(new_value);
    }
}
```

**Output**

```java
1212.121311
```