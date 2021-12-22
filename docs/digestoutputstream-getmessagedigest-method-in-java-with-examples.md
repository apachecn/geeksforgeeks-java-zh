# Java 中的 DigestOutputStream getMessageDigest()方法，带示例

> 原文:[https://www . geesforgeks . org/digestoutputstream-getmessagedigest-method-in-Java-with-examples/](https://www.geeksforgeeks.org/digestoutputstream-getmessagedigest-method-in-java-with-examples/)

**Java . security . DigestOutputStream**类的 **getMessageDigest()** 方法提供了分配给这个 digestoutstream 对象的消息摘要。

**语法:**

```java
public MessageDigest getMessageDigest()
```

**返回值:**该方法返回分配给它的**消息摘要对象**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“name”文件。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个文件“名称”。

以下是说明 **getMessageDigest()** 方法的示例:

**例 1:**

```java
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
            // object of OutputStream
            OutputStream is
                = new FileOutputStream("f:/java/name.txt");

            // creating and initializing
            // object of DigestOutputStream
            DigestOutputStream di
                = new DigestOutputStream(is, sr);

            // getting the message digest
            // using getMessageDigest() method
            MessageDigest str
                = di.getMessageDigest();

            // display the result
            System.out.println("Status : "
                               + str.toString());
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

**输出:**

```java
Status : MD5 Message Digest from SUN, 

```

**例 2:**

```java
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
            // object of OutputStream
            OutputStream is
                = new FileOutputStream("f:/java/name.txt");

            // creating and initializing
            // object of DigestOutputStream
            DigestOutputStream di
                = new DigestOutputStream(is, sr);

            // getting the message digest
            // using getMessageDigest() method
            MessageDigest str
                = di.getMessageDigest();

            // display the result
            System.out.println("Status : "
                               + str.toString());
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

**输出:**

```java
Status : SHA-1 Message Digest from SUN, 

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/digestoutputstream . html # getMessageDigest–](https://docs.oracle.com/javase/9/docs/api/java/security/DigestOutputStream.html#getMessageDigest--)