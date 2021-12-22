# Java 中的 DigestOutputStream.toString()方法，示例

> 原文:[https://www . geesforgeks . org/digestoutputstream-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/digestoutputstream-tostring-method-in-java-with-examples/)

**Java . security . DigestOutputStream**类的 **toString()** 方法，用于以字符串格式提供 digestoutstream 的对象。

**语法:**

```java
public String toString()
```

**返回值:**该方法以字符串形式返回 **DigestOutputStream** 的对象。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“name”文件。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个文件“名称”。

以下是说明 **toString()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// toString() method

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
                = new FileOutputStream(
                    "f:/java/name.txt");

            // creating and initializing
            // object of DigestOutputStream
            DigestOutputStream di
                = new DigestOutputStream(is, sr);

            // getting the string
            // representation of DigestOutputStream
            // using toString() method
            String str = di.toString();

            // display the result
            System.out.println("Status : " + str);
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
Status : [Digest Output Stream] MD5 Message Digest from SUN, 

```

**例 2:**

```java
// Java program to demonstrate
// toString() method

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
                = new FileOutputStream(
                    "f:/java/name.txt");

            // creating and initializing
            // object of DigestOutputStream
            DigestOutputStream di
                = new DigestOutputStream(is, sr);

            // getting the string representation
            // of DigestOutputStream
            // using toString() method
            String str = di.toString();

            // display the result
            System.out.println("Status : " + str);
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
Status : [Digest Output Stream] SHA-1 Message Digest from SUN, 

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/digestoutputstream . html # setMessageDigest-Java . security . messagedigest-](https://docs.oracle.com/javase/9/docs/api/java/security/DigestOutputStream.html#setMessageDigest-java.security.MessageDigest-)