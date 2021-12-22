# Java 中的 MessageDigest getDigestLength()方法，带示例

> 原文:[https://www . geesforgeks . org/messagedigest-getdigest length-method-in-Java-with-examples/](https://www.geeksforgeeks.org/messagedigest-getdigestlength-method-in-java-with-examples/)

**消息摘要**类的 **getDigestLength()** 方法用于获取消息摘要对象的对象大小，单位为字节。

**语法:**

```java
public final int getDigestLength()
```

**返回值:**该方法以字节形式提供消息摘要的长度。

以下是说明 **getDigestLength()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getDigestLength() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating object of MessageDigest
            MessageDigest msd
                = MessageDigest.getInstance("SHA-256", "SUN");

            // getting the length of MessageDigest of object msd
            // by using method getDigestLength()
            int length = msd.getDigestLength();

            // printing the provider name
            System.out.println("Message digest length : "
                               + length);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NoSuchProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Message digest length : 32

```

**例 2:**

```java
// Java program to demonstrate
// getDigestLength() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating object of MessageDigest
            MessageDigest msd
                = MessageDigest.getInstance("MD5");

            // getting the length of MessageDigest of object msd
            // by using method getDigestLength()
            int length = msd.getDigestLength();

            // printing the provider name
            System.out.println("Message digest length : "
                               + length);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Message digest length : 16

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/messagedigest . html # getDigestLength–](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#getDigestLength--)