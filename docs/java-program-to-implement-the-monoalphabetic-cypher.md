# 实现单字母密码的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-implement-the-monalphabetic-cypher/](https://www.geeksforgeeks.org/java-program-to-implement-the-monoalphabetic-cypher/)

单字母密码是一种基于单个字母密钥将纯文本的字母映射为密文字母的密码。这是一对一的映射。

给定纯文本，任务是实现单字母密码。

**示例:**

```
***Input:***  Welcome to geeksforgeeks
***Output:*** Plain text: Welcome to geeksforgeeks
        Encrypted message: VTSEGDT ZG UTTALYGKUTTAL
        Decrypted message: welcome to geeksforgeeks

***Input:***  Live the moment
***Output:*** Plain text: Live the moment
        Encrypted message: SOCT ZIT DGDTFZ
        Decrypted message: live the moment
```

**将字符映射到我们在代码中使用的密文字母:**

<figure class="table">

| **一** | **b** | **c** | **d** | **e** | **f** | **g** | **h** | **i** | **j** |
| Q | W | E | 稀有 | T | Y | U | 我 | O | P |
| **k** | **l** | **米** | **n** | **o** | **p** | **q** | **r** | **s** | **t** |
| A | S | D | F | G | H | J | K | L | Z |
| **u** | **v** | **w** | **x** | **y** | **z** |
| X | C | V | B | 普通 | M |

</figure>

**输出说明:**

<figure class="table">

| **W**–W–V | **t**–Z | **g**–U | **g**–U |
| **e**–T | **o**–G | **e**–T | **e**–T |
| **l**–S |   | **e**–T | **e**–T |
| **c**–E |   | **k**–A | **k**–A |
| **o**–G |   | **s**–L | **s**–L |
| **m**–D |   | **f**–Y |   |
| **e**–T |   | **o**–G |   |
|   |   | **r**–K |   |

</figure>

**欢迎来到极客 forgeeks→**VTSEGDT ZG UTTALYGKUTTAL

**进场:**

**1。**创建两个字符数组，一个用于普通字母(比如 normalChar[])，另一个用于编码(比如 codedChar[])。

**2。**我们将使用两个功能:

*   **stringEncryption:** 我们传递字符串(所有字符都是小写的字符串)作为参数。初始化一个空字符串(比如加密字符串 **)** 。我们使用 for 循环，将每个字符与普通字符数组进行比较，只要条件为真，就将带有相应 codedChar 索引的字符添加到加密字符串中。在特殊字符的情况下，我们将直接将它们添加到字符串中。
*   **字符串加密:**我们将加密的字符串作为参数传递。初始化一个空字符串。同样，我们运行 for 循环，并将具有对应索引 normalChar 的字符添加到解密的字符串中。在特殊字符的情况下，我们将直接将它们添加到字符串中。

**以下是上述方法的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implement the Monoalphabetic Cypher

import java.io.*;
class GFG {
    public static char normalChar[]
        = { 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i',
            'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r',
            's', 't', 'u', 'v', 'w', 'x', 'y', 'z' };

    public static char codedChar[]
        = { 'Q', 'W', 'E', 'R', 'T', 'Y', 'U', 'I', 'O',
            'P', 'A', 'S', 'D', 'F', 'G', 'H', 'J', 'K',
            'L', 'Z', 'X', 'C', 'V', 'B', 'N', 'M' };

    // Function which returns encrypted string
    public static String stringEncryption(String s)
    {
        // initializing an empty String
        String encryptedString = "";

        // comparing each character of the string and
        // encoding each character using the indices
        for (int i = 0; i < s.length(); i++) {
            for (int j = 0; j < 26; j++) {

                // comparing the character and
                // adding the corresponding char
                // to the encryptedString
                if (s.charAt(i) == normalChar[j])
                {
                    encryptedString += codedChar[j];
                    break;
                }

                // if there are any special characters
                // add them directly to the string
                if (s.charAt(i) < 'a' || s.charAt(i) > 'z')
                {
                    encryptedString += s.charAt(i);
                    break;
                }
            }
        }

        // return encryptedString
        return encryptedString;
    }

    // Function which returns descryptedString
    public static String stringDecryption(String s)
    {

        // Initializing the string
        String decryptedString = "";

        // Run the for loop for total string
        for (int i = 0; i < s.length(); i++)
        {
            for (int j = 0; j < 26; j++) {

                // compare each characters and decode them
                // using indices
                if (s.charAt(i) == codedChar[j])
                {
                    decryptedString += normalChar[j];
                    break;
                }

                // Add the special characters directly to
                // the String
                if (s.charAt(i) < 'A' || s.charAt(i) > 'Z')
                {
                    decryptedString += s.charAt(i);
                    break;
                }
            }
        }

        // return the decryptedString
        return decryptedString;
    }
    public static void main(String args[])
    {
        String str = "Welcome to geeksforgeeks";

        // print plain text
        System.out.println("Plain text: " + str);

        // Changing whole string to lower case
        // function call to stringEncryption and storing in
        // encryptedString
        String encryptedString = stringEncryption(str.toLowerCase());

        // printing encryptedString
        System.out.println("Encrypted message: "
                           + encryptedString);

        // function call to stringDecryption and printing
        // the decryptedString
        System.out.println("Decrypted message: "
            + stringDecryption(encryptedString));

    }
}
```

**Output**

```
Plain text: Welcome to geeksforgeeks
Encrypted message: VTSEGDT ZG UTTALYGKUTTAL
Decrypted message: welcome to geeksforgeeks
```