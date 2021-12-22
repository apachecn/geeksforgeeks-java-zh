# 用于 Int 到 Char 转换的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-for-int-to-char-conversion/](https://www.geeksforgeeks.org/java-program-for-int-to-char-conversion/)

给定一个整数 **N** 。任务是将数字转换成字符。

插图:

```java
Input : N = 74254 
Output: Seven four two five four

Input : N = 23 
Output: Two three 
```

**方法:**

1.  不使用模运算符(朴素方法)
2.  使用模运算符(最佳方法)

**进场:**

1.  将数字转换成字符串。
2.  开始遍历字符串，并打印数字的等效字符串。

**实施:**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Convert Number in Characters

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Method 1
    // To convert number to a character
    static void NumbertoCharacter(String s)
    {
        // Iterating the number taking one digit at a time
        // via switch case using length() method
        for (int i = 0; i < s.length(); i++) {

            // Switch case
            // Reading digits obe by one
            // using charAtt() method
            switch (s.charAt(i)) {

            // Case1
            case '1':
                System.out.print("one ");

                // Break statement to hault
                // normal execution of the program
                break;

            // Case 2
            case '2':
                System.out.print("two ");
                break;

            // Case 3
            case '3':
                System.out.print("three ");
                break;

            // Case 4
            case '4':
                System.out.print("four ");
                break;

            // Case 5
            case '5':
                System.out.print("five ");
                break;

            // Case 6
            case '6':
                System.out.print("six ");
                break;

            // Case 7
            case '7':
                System.out.print("seven ");
                break;

            // Case 8
            case '8':
                System.out.print("eight ");
                break;

            // Case 9
            case '9':
                System.out.print("nine ");
                break;

            // Default case
            case '0':
                System.out.print("zero ");
                break;
            default:
                System.out.print("InValid ");
                break;
            }
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input Integer
        int n = 12345;

        // Calling the above function
        NumbertoCharacter(n + "");
    }
}
```

**Output**

```java
one two three four five 
```

**方法 2:** 使用模算子(最优方法)

**程序:**

1.  反转数字。
2.  从右到左迭代反转的数字。
3.  用模数提取最后一个数字，然后用一个开关大小写得到对应的单词。
4.  迭代时将数字除以 10。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Convert Number in Characters

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Method 1
    // To convert numbers to characters
    static void NumbertoCharacter(int n)
    {
        // Initially declaring and initializing
        // reverse of number and remainder to zero
        int rev = 0, r = 0;

        // If number is positive 
        while (n > 0) {

          // For reversal of number

            // The remainder will give
            // the last digit of the number
            r = n % 10;
            rev = rev * 10 + r;
            n = n / 10;
        }

        while (rev > 0) {

            // Extract the first digit
            // of the reversed number
            r = rev % 10;

            // Match it with switch case
            switch (r) {
            case 1:
                System.out.print("one ");
                break;
            case 2:
                System.out.print("two ");
                break;
            case 3:
                System.out.print("three ");
                break;
            case 4:
                System.out.print("four ");
                break;
            case 5:
                System.out.print("five ");
                break;
            case 6:
                System.out.print("six ");
                break;
            case 7:
                System.out.print("seven ");
                break;
            case 8:
                System.out.print("eight ");
                break;
            case 9:
                System.out.print("nine ");
                break;
            case 0:
                System.out.print("zero ");
                break;

            // Default case when above switch cases holds false
            default:
                System.out.print("InValid ");
                break;
            }

            // Divide the number by 10
            // to get the next number
            rev = rev / 10;
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input integer
        int n = 12345;

        // Calling the above fuction(Method1)
        NumbertoCharacter(n);
    }
}
```

**Output**

```java
one two three four five 
```

**时间复杂度:** O(k)，k 是数字的长度。
**空间复杂度:** O(1)