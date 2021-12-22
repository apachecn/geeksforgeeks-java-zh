# 从字符串中分离单个字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-将单个字符从字符串中分离出来/](https://www.geeksforgeeks.org/java-program-to-separate-the-individual-characters-from-a-string/)

字符串是包含空格的字符序列。 [String 的对象在 java 中是不可变的](https://www.geeksforgeeks.org/java-string-is-immutable-what-exactly-is-the-meaning/)，这意味着一旦在字符串中创建了一个对象，它的内容就不能改变。在这个特殊的问题陈述中，我们被要求从作为输入提供的字符串中分离出每个单独的字符。因此，为了将每个字符从字符串中分离出来，通过其索引来访问各个字符。

**示例:**

```
Input : string = "GeeksforGeeks"
Output: Individual characters from given string :
         G e e k s f o r G e e k s
Input : string = "Characters"
Output: Individual characters from given string :
         C h a r a c t e r s
```

**方法 1:**

1.  首先，定义一个字符串。
2.  接下来，创建一个 for 循环，其中循环变量将从索引 0 开始，到给定字符串的长度结束。
3.  打印每个索引处出现的字符，以便分隔每个单独的字符。
4.  为了更好地可视化，用空格分隔每个单独的字符。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Separate the
// Individual Characters from a String

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        String string = "GeeksforGeeks";

        // Displays individual characters from given string
        System.out.println(
            "Individual characters from given string: ");

        // Iterate through the given string to
        // display the individual characters
        for (int i = 0; i < string.length(); i++) {
            System.out.print(string.charAt(i) + " ");
        }
    }
}
```

**Output**

```
Individual characters from given string: 
G e e k s f o r G e e k s 
```

**时间复杂度:** O(n)，其中 n 为字符串的长度。

**方法 2:**

1.  定义一个字符串。
2.  使用 **toCharArray** 方法，将返回的字符数组存储在字符数组中。
3.  使用 for-each 循环打印分隔字符。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Implementation of the above approach

import java.io.*;

class GFG
{
    public static void main(String[] args)
    {
         // Initialising String
        String str = "GeeksForGeeks";

        // Converts the string into
         // char array
        char[] arr = str.toCharArray();

        System.out.println(
            "Displaying individual characters"
             + "from given string:");

        // Printing the characters using for-each loop
        for (char e : arr)
            System.out.print(e + " ");
    }
}
```

**Output**

```
Displaying individual charactersfrom given string:
G e e k s F o r G e e k s 
```

**时间复杂度:**O(N)
T3】空间复杂度: O(N)