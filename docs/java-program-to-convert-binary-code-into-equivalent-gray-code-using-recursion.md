# 使用递归将二进制代码转换为等效格雷码的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-binary-code-to-equal-gray-code-use-recursion/](https://www.geeksforgeeks.org/java-program-to-convert-binary-code-into-equivalent-gray-code-using-recursion/)

使用递归将数字的二进制代码转换为等效的格雷码。二进制是存储数字的默认方式，但是在许多应用程序中，二进制数字没有用，需要二进制的变体。格雷码具有两个连续数字仅相差一位的特性，用于 K 图、纠错和通信。

**例:**

```
Input:    1101
Output:    1011

Input:    11010001
Output:    10111001

```

**方法#1:整数限制下的数字**

**算法:**

1.  如果 n=0，则灰色=0。
2.  否则，如果最后两位是相反的，那么 gray = 1+(10 * binary gray(n/10))。
3.  否则，如果最后两位相同，那么 gray = 10 * binary gray(n/10)

下面是上述方法的实现。

## 爪哇

```
// Java Program to Convert Binary Code
// Into Equivalent Gray Code Using Recursion
import java.io.*;
class GFG {

    // Function to change Binary Code
    // to Gray using Recursion
    public static int binaryToGray(int n)
    {
        if (n == 0) {
            return 0;
        }
        // Extracting the last digit
        int a = n % 10;
        // Extracting the second last digit
        int b = (n / 10) % 10;
        // Else If last two digits
        // are opposite bits to each other
        if ((a & ~b) == 1 || (~a & b) == 1) {
            return (1 + 10 * binaryToGray(n / 10));
        }
        // Else If the last
        // two bits are same
        return (10 * binaryToGray(n / 10));
    }
    // Driver's Function
    public static void main(String[] args)
    {
        int binaryNumber = 11010001;
        int result = binaryToGray(binaryNumber);
        System.out.println("Gray Code is " + result);
    }
}
```

**输出**

```
Gray Code is 10111001

```

**方法#2:大二进制数**

**算法:**

1.  Enter in string format.
2.  Pass the current pointer in a recursive function.
3.  Store the XOR of the I-th bit and the (i-1)-th bit in the array.
4.  Returns an array at the end of recursion.

下面是上述方法的实现。

## 爪哇

```
// Java Program to Convert Binary Code
// Into Equivalent Gray Code Using Recursion
import java.io.*;
class GFG {
    // XOR two numbers
    public static char xor(char a, char b)
    {
        if (a == b)
            return '0';
        else
            return '1';
    }
    // Recursive function Gray code conversion
    public static char[] ans(char[] kp, String str, int i)
    {
        if (i == str.length())
            return kp;
        kp[i] = xor(str.charAt(i), str.charAt(i - 1));
        i++;
        return ans(kp, str, i);
    }
    // Driver Program
    public static void main(String args[])
    {
        String str = "01001";
        char[] kp = new char[str.length()];
        kp[0] = str.charAt(0);

        // Recursive function call
        ans(kp, str, 1);

        // Print Gray Code
        System.out.print("Gray Code is ");
        for (char i : kp)
            System.out.print(i + "");
    }
}
```

**输出**

```
Gray Code is 01101
```

**时间复杂度:** O(N)，其中 N 为二进制码的长度。