# 实现一次性 Pad 算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-实现一次性填充算法的程序/](https://www.geeksforgeeks.org/java-program-to-implement-the-one-time-pad-algorithm/)

One Time Pad 算法也被称为 [**【弗南密码】**](https://www.geeksforgeeks.org/vernam-cipher-in-cryptography/) 。这是一种加密字母纯文本的方法。它是将纯文本转换为密文的换位技术之一。在这个机制中，我们给纯文本的每个字符分配一个数字。

**赋值如下:**

<figure class="table">

| **A** | **B** | **C** | **D** | **E** | **F** | **G** | **H** | **I** | **J** |
| Zero | one | Two | three | four | five | six | seven | eight | nine |
| **K** | **L** | **M** | **N** | **O** | **P** | **Q** | **R** | **S** | **T** |
| Ten | Eleven | Twelve | Thirteen | Fourteen | Fifteen | Sixteen | Seventeen | Eighteen | Nineteen |
| **U** | **V** | **W** | **X** | **Y** | **Z** |
| Twenty | Twenty-one | Twenty-two | Twenty-three | Twenty-four | Twenty-five |

</figure>

**密钥与纯文本的关系:**在该算法中，密钥的长度应等于纯文本的长度。

**示例:**

```
***Input:** * plain text - HELLO
        Key - MONEY
***Output:*** Cipher - TSYPM
        Message - HELLO

***Input:***  plain text - SAVE
        Key - LIFE  
***Output:*** Cipher - DIAI        
        Message - SAVE
```

**以上解释:**

**第 1 部分(纯文本到密文)**

> 纯文本-h 和 l o→7 4 11 14
> 
> Key — M 或 n 和 Y → 12 14 13 4 24
> 
> 纯文本+按键→ 19 18 24 15 38
> 
> →19 18 24 15 12(-38-26)

**密文→ T S Y P M**

**第 2 部分(密文到消息)**

> 密文— T S Y P M → 19 18 24 15 12
> 
> Key — M 或 n 和 Y→ 12 14 13 4 24
> 
> 密文-密钥→ 7 4 11 11 -12
> 
> →7 4 11 14

**留言→ H 和 l l**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program which implements
// one time pad algorithm

import java.io.*;
public class GFG {

    // function which returns encryptedText
    public static String stringEncryption(String text,
                                          String key)
    {

        // initializing cipherText
        String cipherText = "";

        // initialize cipher array of key length
        // which stores the sum of corresponding no.'s
        // of plainText and key.
        int cipher[] = new int[key.length()];

        for (int i = 0; i < key.length(); i++)
        {
            cipher[i] = text.charAt(i) - 'A' + key.charAt(i)
                        - 'A';
        }

        // if the sum is greater than 25
        // subtract 26 from it and store that resulting
        // value
        for (int i = 0; i < key.length(); i++)
        {
            if (cipher[i] > 25)
            {
                cipher[i] = cipher[i] - 26;
            }
        }

        // convert the no.'s into integers
        // convert these integers to corresponding
        // characters and add them up to cipherText
        for (int i = 0; i < key.length(); i++) 
        {
            int x = cipher[i] + 'A';
            cipherText += (char)x;
        }

        // returning the cipherText
        return cipherText;
    }

    // function which returns plainText
    public static String stringDecryption(String s,String key)
    {
        // initializing plainText
        String plainText = "";

        // initializing integer array of key length
        // which stores difference of corresponding no.'s of
        // each character of cipherText and key
        int plain[] = new int[key.length()];

        // running for loop for each character
        // subtracting and storing in the array
        for (int i = 0; i < key.length(); i++) 
        {
            plain[i]= s.charAt(i) - 'A' - (key.charAt(i) - 'A');
        }

        // if the difference is less than 0
        // add 26 and store it in the array.
        for (int i = 0; i < key.length(); i++)
        {
            if (plain[i] < 0) 
            {
                plain[i] = plain[i] + 26;
            }
        }

        // convert int to corresponding char
        // add them up to plainText
        for (int i = 0; i < key.length(); i++)
        {
            int x = plain[i] + 'A';
            plainText += (char)x;
        }

        // returning plainText
        return plainText;
    }

    // main function
    public static void main(String[] args)
    {

        // declaration of plain text
        String plainText = "Hello";

        // declaration of key
        String key = "MONEY";

        // converting plain text to toUpperCase
        // function call to stringEncryption
        // with plainText and key as parameters
        String encryptedText = 
               stringEncryption(plainText.toUpperCase(), key.toUpperCase());

        // printing cipher Text
        System.out.println("Cipher Text - "+ encryptedText);

        // function call to stringDecryption
        // with encryptedText and key as parameters
        System.out.println("Message - "
                 + stringDecryption(encryptedText,
                                    key.toUpperCase()));
    }
}
```

**Output**

```
Cipher Text - TSYPM
Message - HELLO
```