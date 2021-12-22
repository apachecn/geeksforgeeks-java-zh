# Java 中的 DigestInputStream.toString()方法，带示例

> 原文:[https://www . geesforgeks . org/digestinputstream-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/digestinputstream-tostring-method-in-java-with-examples/)

**Java . security . DigestInputStream**类的 **toString()** 方法提供字符串格式的 DigestInputStream 对象。
**语法:**

```java
public String toString()
```

**返回值:**该方法以字符串格式返回 DigestInputStream 的对象。
**注意:**本文中的所有程序都不会在在线 IDE 上运行，因为不存在“name”文件。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个文件“名称”。
以下是举例说明 **toString()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // object of InputStream
            InputStream is
                = new FileInputStream("f:/java/name.txt");

            // creating and initializing
            // object of DigestInputStream
            DigestInputStream di
                = new DigestInputStream(is, sr);

            // getting the string representation
            // of DigestInputStream
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

**Output:** 

```java
Status : [Digest Input Stream] MD5 Message Digest from SUN, 
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // object of InputStream
            InputStream is
                = new FileInputStream("f:/java/name.txt");

            // creating and initializing
            // object of DigestInputStream
            DigestInputStream di
                = new DigestInputStream(is, sr);

            // getting the string
            // representation of DigestInputStream
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

**Output:** 

```java
Status : [Digest Input Stream] SHA-1 Message Digest from SUN, 
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/security/digestinputstream . html # toString–T4】