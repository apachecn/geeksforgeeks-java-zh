# Java 中的 DigestInputStream getMessageDigest()方法，带示例

> 原文:[https://www . geesforgeks . org/digest inputstream-getmessagedigest-method-in-Java-with-examples/](https://www.geeksforgeeks.org/digestinputstream-getmessagedigest-method-in-java-with-examples/)

**Java . security . DigestInputStream**类的 **getMessageDigest()** 方法提供了分配给这个 DigestInputStream 对象的消息摘要。

**语法:**

```
public MessageDigest getMessageDigest()
```

**返回值:**这个方法返回分配给它的 MessageDigest 对象。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“name”文件。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个文件“名称”。

以下是说明 **getMessageDigest()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance("MD5");

            // creating and initializing
            // object of InputStream
            InputStream is
                = new FileInputStream("f:/java/name.txt");

            // creating and initializing
            // object of DigestInputStream
            DigestInputStream di
                = new DigestInputStream(is, sr);

            // getting the message digest
            // using getMessageDigest() method
            MessageDigest str = di.getMessageDigest();

            // display the result
            System.out.println("Status : " + str.toString());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (FileNotFoundException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Status : MD5 Message Digest from SUN, 
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            MessageDigest sr
                = MessageDigest.getInstance("SHA-1");

            // creating and initializing
            // object of InputStream
            InputStream is
                = new FileInputStream("f:/java/name.txt");

            // creating and initializing// object of DigestInputStream
                DigestInputStream di
                = new DigestInputStream(is, sr);

            // getting the message digest
            // using getMessageDigest() method
            MessageDigest str = di.getMessageDigest();

            // printing the status
            System.out.println("Status : " + str.toString());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (FileNotFoundException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Status : SHA-1 Message Digest from SUN, 
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/security/digestinputstream . html # getMessageDigest–T4】