# 定制建筑加密算法(混合加密)

> 原文:[https://www . geesforgeks . org/custom-building-密码学-算法-混合-密码学/](https://www.geeksforgeeks.org/custom-building-cryptography-algorithms-hybrid-cryptography/)

> 密码学可以被定义为一种编码和解码模式(以消息的形式)的艺术。

密码学是一个非常简单的概念，它处理对字符串(或文本)的操作，使它们对于中间人员来说不可读。它有一个非常有效的方法来对来自其他方的文本进行加密或解密。一些例子是，凯撒密码，维格纳密码，柱状密码，DES，AES 和名单继续。为了开发定制的加密算法，可以使用混合加密算法。

**混合加密(Hybrid Encryption)是密码学中的一个概念，它结合/合并一个/两个密码算法来生成更有效的加密文本。**

示例:

**FibBil 密码算法**

***问题陈述:***

程序生成一个加密文本，通过计算斐波那契数列，将斐波那契数列的项与每个明文字母相加，直到密钥的长度。

***算法:***

**对于加密:**从用户处获取输入的纯文本和密钥，反转纯文本并将纯文本与密钥连接起来，将字符串复制到数组中。复制后，将数组元素分成两部分，EvenArray 和 OddArray，其中数组的偶数索引将放在 EvenArray 中，对于 OddArray 也是如此。开始生成斐波那契数列 F(i)直到密钥的长度 **<sub>j</sub>** 这样 **c=i+j** 其中 c 是带有 mod 26 的密文。在一个密码字符串中添加所有的 c元素，这样加密就完成了！。使用总结概念时，突出了实现凯撒密码。

**用于解密:**加密算法反之亦然

***算法示例:***

> **输入:** *你好*
> T5】键: *abcd*
> **输出:** *riobkxezg*
> 反转输入，olleh，用键即 ollehabcd 追加此。
> even string:leac
> odd string:olhbd
> 由于键长为 4，会产生 4 次循环，包括 FibNum 0，忽略。
> **代表偶数数组密码:**
> **fibn:1**
> 在偶数数组中代表 l，fibn 1 CIP 是 k
> 在偶数数组中代表 e，fibn 1 CIP 是 d
> 在偶数数组中代表 a，fibn 1 CIP 是 z
> 在偶数数组中代表 c，fibn 1 CIP 是 b
> **fibn:2**
> 在偶数数组中代表 l，FibNum 2 cip e 和 FibNum 2 cip 是 c
> 在偶数数组中为 a，FibNum 2 cip 是 y
> 在偶数数组中为 c，FibNum 2 cip 是 a
> **FibNum: 3** (最终计算字母)
> **在偶阵中为 l 而 fibn 3 CIP 为 i**
> **在偶阵中为 e 而 fibn 3 CIP 为 b**
> **在偶阵中为 a 而 fibn 3 CIP 为 x**
> **在偶阵中为 c 而 fibn 3 CIP 为 z**
> **为 Odd Array CIPS**
> T54】fibn:1
> 在 l 和 fibn 1 CIP 的奇数数组是 m
> 在 h 的奇数数组中，fibn 1 CIP 是 i
> 在 b 的奇数数组中，fibn 1 CIP 是 c
> 在 d 的奇数数组中，fibn 1 CIP 是 e
> **fibn:**2
> 在 o 的奇数数组中，fibn 2 CIP 是 q
> 在 l 的奇数数组中，fibn 2 CIP 是 n
> 在奇数数组中 在 b 的奇数数组中 fibn 2 CIP 是 j
> ，在 d 的奇数数组中 fibn 2 CIP 是 d
> ，fibn 2 CIP 是 f
> **fibn:**3(最终计算字母)
> **奇数阵中为 o，fibn 3 CIP 为 r**
> **奇数阵中为 l，fibn 3 CIP 为 o**
> **奇数阵中为 h，fibn 3 CIP 为 k**
> **奇数阵中为 b，fibn 3 CIP 为 e**
> **奇数阵中为 d，fibn 3 CIP 为 g**
> 
> 按照索引顺序排列 EvenArrayCiphers 和 OddArrayCiphers，因此最终的字符串密码将是， **riobkxezg**

***程序:***

## C++14

```
#include<bits/stdc++.h>
using namespace std;

string encryptText(string password, string key)
{
    int a = 0, b = 1, c = 0,
        m = 0, k = 0, j = 0;
    string cipher = "", temp = "";

    // Declare a password string
    string pw = password;

    // Reverse the String
    reverse(pw.begin(), pw.end());
    pw = pw + key;

    // For future Purpose
    temp = pw;
    string stringArray = temp;
    string evenString = "", oddString = "";

    // Declare EvenArray for storing
    // even index of stringArray
    string evenArray;

    // Declare OddArray for storing
    // odd index of stringArray
    string oddArray;

    // Storing the positions in their
    // respective arrays
    for(int i = 0;
            i < stringArray.length(); i++)
    {
        if (i % 2 == 0)
        {
            oddString = oddString +
                        stringArray[i];
        }
        else
        {
            evenString = evenString +
                         stringArray[i];
        }
    }

    evenArray = new char[evenString.length()];
    oddArray = new char[oddString.length()];

    // Generate a Fibonacci Series
    // Upto the Key Length
    while (m <= key.length())
    {

        // As it always starts with 1
        if (m == 0)
            m = 1;

        else
        {

            // Logic For Fibonacci Series
            a = b;
            b = c;
            c = a + b;

            for(int i = 0;
                    i < evenString.length();
                    i++)
            {

                // Caesar Cipher Algorithm Start
                // for even positions
                int p = evenString[i];
                int cip = 0;

                if (p == '0' || p == '1' ||
                    p == '2' || p == '3' ||
                    p == '4' || p == '5' ||
                    p == '6' || p == '7' ||
                    p == '8' || p == '9')
                {
                    cip = p - c;

                    if (cip < '0')
                        cip = cip + 9;
                }
                else
                {
                    cip = p - c;
                    if (cip < 'a')
                    {
                        cip = cip + 26;
                    }
                }
                evenArray[i] = (char)cip;

                // Caesar Cipher Algorithm End
            }
            for(int i = 0;
                    i < oddString.length();
                    i++)
            {

                // Caesar Cipher Algorithm
                // Start for odd positions
                int p = oddString[i];
                int cip = 0;

                if (p == '0' || p == '1' ||
                    p == '2' || p == '3' ||
                    p == '4' || p == '5' ||
                    p == '6' || p == '7' ||
                    p == '8' || p == '9')
                {
                    cip = p + c;
                    if (cip > '9')
                        cip = cip - 9;
                }
                else
                {
                    cip = p + c;
                    if (cip > 'z')
                    {
                        cip = cip - 26;
                    }
                }
                oddArray[i] = (char)cip;

                // Caesar Cipher Algorithm End
            }
            m++;
        }
    }

    // Storing content of even and
    // odd array to the string array
    for(int i = 0; i < stringArray.size(); i++)
    {
        if (i % 2 == 0)
        {
            stringArray[i] = oddArray[k];
            k++;
        }
        else
        {
            stringArray[i] = evenArray[j];
            j++;
        }
    }

    // Generating a Cipher Text
    // by stringArray (Caesar Cipher)
    for(char d : stringArray)
    {
        cipher = cipher + d;
    }

    // Return the Cipher Text
    return cipher;
}

// Driver code
int main()
{
    string pass = "hello";
    string key = "abcd";

    cout << encryptText(pass, key);

    return 0;
}

// This code is contributed by himanshu77
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;
import java.lang.*;

class GFG {

    public static void main(String[] args)
    {
        String pass = "hello";
        String key = "abcd";
        System.out.println(encryptText(pass, key));
    }
    public static String encryptText(String password, String key)
    {
        int a = 0, b = 1, c = 0, m = 0, k = 0, j = 0;
        String cipher = "", temp = "";

        // Declare a password string
        StringBuffer pw = new StringBuffer(password);

        // Reverse the String
        pw = pw.reverse();
        pw = pw.append(key);

        // For future Purpose
        temp = pw.toString();
        char stringArray[] = temp.toCharArray();
        String evenString = "", oddString = "";

        // Declare EvenArray for storing
        // even index of stringArray
        char evenArray[];

        // Declare OddArray for storing
        // odd index of stringArray
        char oddArray[];

        // Storing the positions in their respective arrays
        for (int i = 0; i < stringArray.length; i++) {
            if (i % 2 == 0) {
                oddString = oddString + Character.toString(stringArray[i]);
            }
            else {
                evenString = evenString + Character.toString(stringArray[i]);
            }
        }
        evenArray = new char[evenString.length()];
        oddArray = new char[oddString.length()];

        // Generate a Fibonacci Series
        // Upto the Key Length
        while (m <= key.length()) {
            // As it always starts with 1
            if (m == 0)
                m = 1;

            else {

                // Logic For Fibonacci Series
                a = b;
                b = c;
                c = a + b;
                for (int i = 0; i < evenString.length(); i++) {
                    // Caesar Cipher Algorithm Start for even positions
                    int p = evenString.charAt(i);
                    int cip = 0;
                    if (p == '0' || p == '1' || p == '2' || p == '3' || p == '4'
                        || p == '5' || p == '6'
                        || p == '7' || p == '8' || p == '9') {
                        cip = p - c;
                        if (cip < '0')
                            cip = cip + 9;
                    }
                    else {
                        cip = p - c;
                        if (cip < 'a') {
                            cip = cip + 26;
                        }
                    }
                    evenArray[i] = (char)cip;
                    /* Caesar Cipher Algorithm End*/
                }
                for (int i = 0; i < oddString.length(); i++) {
                    // Caesar Cipher Algorithm Start for odd positions
                    int p = oddString.charAt(i);
                    int cip = 0;
                    if (p == '0' || p == '1' || p == '2' || p == '3' || p == '4'
                        || p == '5' || p == '6'
                        || p == '7' || p == '8' || p == '9') {
                        cip = p + c;
                        if (cip > '9')
                            cip = cip - 9;
                    }
                    else {
                        cip = p + c;
                        if (cip > 'z') {
                            cip = cip - 26;
                        }
                    }
                    oddArray[i] = (char)cip;
                    // Caesar Cipher Algorithm End
                }

                m++;
            }
        }

        // Storing content of even and
        // odd array to the string array
        for (int i = 0; i < stringArray.length; i++) {
            if (i % 2 == 0) {
                stringArray[i] = oddArray[k];
                k++;
            }
            else {
                stringArray[i] = evenArray[j];
                j++;
            }
        }
        // Generating a Cipher Text
        // by stringArray (Caesar Cipher)
        for (char d : stringArray) {
            cipher = cipher + d;
        }

        // Return the Cipher Text
        return cipher;
    }
}
```

**Output:** 

```
riobkxezg
```

***结论:***

密码学的混合算法是有效的，因此，检测模式和解码消息不是很容易。这里，算法是数学函数和凯撒密码的结合，从而实现混合密码算法。