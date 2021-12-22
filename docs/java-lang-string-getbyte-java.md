# Java 中的 Java.lang.String.getByte()

> 原文:[https://www . geesforgeks . org/Java-lang-string-getbyte-Java/](https://www.geeksforgeeks.org/java-lang-string-getbyte-java/)

java 中的 getbytes()函数用于将字符串转换为字节序列，并返回字节数组。该功能可以通过两种方式实现。本文将讨论这两种方法。

1.  **Syntax 1 – public byte[] getBytes() :** This function takes no arguments and used default charset to encode the string into bytes.

    ```
    // Java code to demonstrate the working of
    // getByte()
    public class GetByte {

    public static void main(String args[])
        {
            // Initializing String
            String gfg = "ASTHA GFG";

            // Displaying string values before
            // conversion
            System.out.println("The String before conversion is : ");
            System.out.println(gfg);

            // converting the string into byte
            // using getBytes ( converts into ASCII values )
            byte[] b = gfg.getBytes();

            // Displaying converted string after conversion
            System.out.println("The String after conversion is : ");
            for (int i = 0; i < b.length; i++) {
                System.out.print(b[i]);
            }
        }
    }
    ```

    输出:

    ```
    The String before conversion is : 
    ASTHA GFG
    The String after conversion is : 
    658384726532717071

    ```

2.  **Syntax 2 : public byte[] getBytes(Charset charset):** This implementation accepts the charset according to which string has to be encoded while conversion into bytes. There are many charset defined and are discussed below.
    *   **美国-ASCII:** 七位 ASCII，又名 ISO646-美国，又名 Unicode 字符集的基本拉丁块
    *   **ISO-8859-1:** ISO 拉丁字母 1 号，a.k.a. ISO-LATIN-1
    *   **UTF-8:** 八位 UCS 转换格式
    *   **UTF-16BE:** 十六位 UCS 转换格式，大端字节顺序
    *   **UTF-16LE:** 十六位 UCS 转换格式，小端字节顺序
    *   **UTF-16:** 十六位 UCS 转换格式，字节顺序由可选的字节顺序标记标识。

    ```
    // Java code to demonstrate the working of
    // getByte() using different character sets
    import java.io.*;
    public class GetBytecharset {

    public static void main(String args[])
        {
            // Initializing String
            String gfg = new String("ASTHA GFG");

            // Displaying string values before
            // conversion
            System.out.println("The String before conversion is : ");
            System.out.println(gfg);

            try {

                // converting the string into byte
                // using getBytes ( converts into UTF-16 values )
                byte[] b = gfg.getBytes("UTF-16");

                // Displaying converted string after conversion
                // into UTF-16
                System.out.println("The String after conversion into UTF-16 is : ");
                for (int i = 0; i < b.length; i++) {
                    System.out.print(b[i]);
                }

                System.out.print("\n");

                // converting the string into byte
                // using getBytes ( converts into UTF-16BE values )
                byte[] c = gfg.getBytes("UTF-16BE");

                // Displaying converted string after conversion
                // into UTF-16BE
                System.out.println("The String after conversion into UTF-16BE is : ");
                for (int i = 0; i < c.length; i++) {
                    System.out.print(c[i]);
                }
            }
            catch (UnsupportedEncodingException g) {
                System.out.println("Unsupported character set" + g);
            }
        }
    }
    ```

    输出:

    ```
    The String before conversion is : 
    ASTHA GFG
    The String after conversion into UTF-16 is : 
    -2-1065083084072065032071070071
    The String after conversion into UTF-16BE is : 
    065083084072065032071070071

    ```

    本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。