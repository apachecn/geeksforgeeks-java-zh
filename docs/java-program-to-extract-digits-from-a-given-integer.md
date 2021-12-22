# 从给定整数中提取数字的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-从给定整数中提取数字的程序/](https://www.geeksforgeeks.org/java-program-to-extract-digits-from-a-given-integer/)

**问题陈述:**对于任何考虑到的随机数，目标是访问该数的每个数字。

**图解:**简单地取两个数字，即 12345 和 110102，绝对随机选择其中一个进行计算，如图所示:

```java
Input: 12345

Output: 1  // 1 digit
    2  // Digit next to 1st digit
    3
    4
    5  // Last Digit of the number 

Input: 110102

Output: 1
    1
    0
    1
    0
    2

```

现在，为了访问数字的位数，有几种方法，从强力方法到最佳方法。两种标准方法如下:

**接近:**

*   使用[整数到字符串](https://www.geeksforgeeks.org/integer-tostring-in-java/)函数(使用内置方法)
*   使用模运算符

**方法 1:使用** [**方法**](https://www.geeksforgeeks.org/integer-tostring-in-java/)

这个方法是一个已经存在于 java 目录中的内置方法，它返回字符串对象。这个字符串对象代表整数值。

**语法:**因为字符串在 java 中是不可变的，这意味着字符串在 Java 中是一个类。**T3】所以，**

```java
public static String toString()

```

它所在的目录如下:

```java
java.lang.Integer.toString()

```

**返回方法:**如上文语法本身所示，该方法返回应用该方法的整数值的字符串对象。也

在这种方法中，我们将整数转换成字符串，然后遍历字符串。

1.  取整数输入。
2.  将输入转换为字符串数据。
3.  遍历字符串，并在每个数字位置打印字符。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Extract Digits from A Given Integer

// Importing Libraries
import java.util.*;
import java.io.*;

class GFG {

    // Main driver function
    public static void main(String[] args)
    {
        // Declaring the number
        int number = 110102;

        // Converting the integer input to string data
        String string_number = Integer.toString(number);

        // Traversing through the string using for loop
        for (int i = 0; i < string_number.length(); i++) {

            // Printing the characters at each position
            System.out.println(string_number.charAt(i));
        }
    }
}
```

**输出:**

```java
1
1
0
1
0
2

```

**方法 2:** 使用模运算符

不使用内置方法无论何时涉及到数字提取，直接以 10 为模就是答案，因为它提取出最后一个数字。类似地，如果对移除已经提取的数字后获得的数字执行该过程，将从小数字中提取出最后一个数字。重复相同的过程，直到提取结束。所以，

在这种方法中**、**从数字中去掉最后一个数字，并一直进行到最后一个数字。

1.  取整数输入。
2.  找到数字的最后一位。
3.  打印获得的最后一位数字，然后将其从数字中删除。
4.  继续跟着第二步和第三步，直到我们到达最后一个数字。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Extract Digits from A Given Integer

// Importing Libraries
import java.util.*;
import java.io.*;

class GFG {

    // Main driver function
    public static void main(String[] args)
    {

        // Declaring the number
        int number = 110102;

        // Printing the last digit of the number
        while (number > 0) {

            // Finding the remainder (Last Digit)
            int remainder = number % 10;

            // Printing the remainder/current last digit
            System.out.println(remainder);

            // Removing the last digit/current last digit
            number = number / 10;
        }
    }
}
```

**输出:**

```java
2
0
1
0
1
1

```