# 如何在 Java 中生成文件的 MD5 校验和？

> 原文:[https://www . geesforgeks . org/如何生成-MD5-Java 文件校验和/](https://www.geeksforgeeks.org/how-to-generate-md5-checksum-for-files-in-java/)

一个字母数字值，即唯一定义文件内容的字母和数字序列，称为校验和(通常称为散列)。校验和通常用于检查从外部源下载的文件的完整性。如果您知道原始版本的校验和，您可以使用校验和实用程序来确保您的副本是等效的。例如，在备份您的文件之前，您可以生成这些文件的校验和，并且一旦您必须在其他设备上下载它们，就可以验证这些校验和。如果文件在过程中被损坏或更改，校验和将会不同。

MD5 和 SHA 是两种最广泛使用的校验和算法。检查校验和时，必须确保使用与生成校验和相同的算法。例如，文件的 MD5 校验和值与其 SHA-256 校验和值完全不同。

为了产生校验和，你运行一个程序，通过一个算法把那个文件。用于此的典型算法包括 MD5、SHA-1、SHA-256 和 SHA-512。

这些算法使用加密哈希函数，该函数接受输入并生成固定长度的字母数字字符串，而不管文件的大小。

> **注意:**
> 
> 1.  Even minor changes in the file can produce different checksums.
> 2.  However, these cryptographic hash functions are not perfect. Security researchers found the "conflict" between MD5 and SHA-1 functions. They found two different files, which produced the same MD5 or SHA-1 hash, but they were different. It is highly unlikely that this will happen only by chance, but attackers can use this strategy to disguise malicious files as valid files.

**在 Java 中生成校验和**

Java 通过 Java 安全包中的消息摘要类提供了生成这些散列函数的内置功能。消息摘要是加密的单向散列函数，它接受任意大小的数据并产生固定长度的散列值。

*   We first instantiate the MessageDigest object by passing any valid hash algorithm string.
*   Then we update this object until we read the complete file. Although we can use the digest (byte[] input) to create the final update of the MessageDigest object by reading the whole file at one time when the file is too large, we may not have enough memory to read the whole file as a byte array, which may lead to *java.lang.out of memory error: Java heap space* .
*   Therefore, it is best to read data in sections and update MessageDigest.

更新完成后，将调用其中一个摘要方法来完成哈希计算。每当调用摘要方法时，MessageDigest 对象都会重置为其初始化状态。摘要方法返回一个字节数组，该数组包含十进制格式的字节，因此我们将其转换为十六进制格式。最后一个字符串是校验和。

**例:**

## 爪哇

```
// Java program to Generate MD5 Checksum for Files

import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;

public class GFG {

    // this method gives a NoSuchAlgorithmException in case
    // we pass a string which dosen't have any hashing
    // algorithm in its correspondence

    public static void main(String[] args)
        throws IOException, NoSuchAlgorithmException
    {

        // create a file object referencing any file from
        // the system of which checksum is to be generated
        File file = new File("C:\\Users\\Raghav\\Desktop\\GFG.txt");

        // instantiate a MessageDigest Object by passing
        // string "MD5" this means that this object will use
        // MD5 hashing algorithm to generate the checksum
        MessageDigest mdigest = MessageDigest.getInstance("MD5");

        // Get the checksum
        String checksum = checksum(mdigest, file);

        // print out the checksum
        System.out.println(checksum);
    }

    // this method return the complete  hash of the file
    // passed
    private static String checksum(MessageDigest digest,
                                   File file)
        throws IOException
    {
        // Get file input stream for reading the file
        // content
        FileInputStream fis = new FileInputStream(file);

        // Create byte array to read data in chunks
        byte[] byteArray = new byte[1024];
        int bytesCount = 0;

        // read the data from file and update that data in
        // the message digest
        while ((bytesCount = fis.read(byteArray)) != -1)
        {
            digest.update(byteArray, 0, bytesCount);
        };

        // close the input stream
        fis.close();

        // store the bytes returned by the digest() method
        byte[] bytes = digest.digest();

        // this array of bytes has bytes in decimal format
        // so we need to convert it into hexadecimal format

        // for this we create an object of StringBuilder
        // since it allows us to update the string i.e. its
        // mutable
        StringBuilder sb = new StringBuilder();

        // loop through the bytes array
        for (int i = 0; i < bytes.length; i++) {

            // the following line converts the decimal into
            // hexadecimal format and appends that to the
            // StringBuilder object
            sb.append(Integer
                    .toString((bytes[i] & 0xff) + 0x100, 16)
                    .substring(1));
        }

        // finally we return the complete hash
        return sb.toString();
    }
}
```

**输出:**

```
8eeecb74627e963d65d10cbf92a2b7c9
```