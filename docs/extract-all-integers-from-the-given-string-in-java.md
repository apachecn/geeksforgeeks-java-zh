# 在 Java 中提取给定字符串中的所有整数

> 原文:[https://www . geesforgeks . org/从给定的 java 字符串中提取所有整数/](https://www.geeksforgeeks.org/extract-all-integers-from-the-given-string-in-java/)

给定一个由数字、字母和特殊字符组成的字符串。任务是从给定的字符串中提取所有的整数。

**示例:**

> **输入:** str = "geeksforgeeks A-118，Sector-136，北方邦-201305"
> **输出:** 118 136 201305
> 
> **输入:**str = " 1ab c35 de 99 ffh，dd11 "
> T3】输出: 1 35 99 11

**进场:**

*   用空格(" ")替换所有非数字字符。
*   现在用一个空格替换每组连续的空格。
*   去掉前导空格和尾随空格(如果有)，最后的字符串将只包含所需的整数。

下面是上述方法的实现:

```
// Java implementation of the approach
public class GFG {

    // Function to return the modified string
    static String extractInt(String str)
    {
        // Replacing every non-digit number
        // with a space(" ")
        str = str.replaceAll("[^\\d]", " ");

        // Remove extra spaces from the beginning
        // and the ending of the string
        str = str.trim();

        // Replace all the consecutive white
        // spaces with a single space
        str = str.replaceAll(" +", " ");

        if (str.equals(""))
            return "-1";

        return str;
    }

    // Driver code
    public static void main(String[] args)
    {
        String str = "avbkjd1122klj4 543 af";
        System.out.print(extractInt(str));
    }
}
```

**Output:**

```
1122 4 543

```