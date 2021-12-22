# Java 中的 MessageDigest toString()方法，带示例

> 原文:[https://www . geesforgeks . org/messagedigest-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/messagedigest-tostring-method-in-java-with-examples/)

**Java . security . messagedigest**类的 **toString()** 方法用于以字符串格式提供消息摘要的对象。

**语法:**

```
public String toString()
```

**返回值:**该方法以字符串形式返回消息摘要的对象。

以下是说明 **toString()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// toString() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating object of MessageDigest
            MessageDigest msd1
                = MessageDigest.getInstance("MD5");

            // getting the string value of msd1
            // using toString() method
            String nv = msd1.toString();

            // display the result
            System.out.println("MessageDigest : "
                               + nv);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出:**

```
MessageDigest : MD5 Message Digest from SUN, <initialized>

```

**例 2:**

```
// Java program to demonstrate
// toString() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating object of MessageDigest
            MessageDigest msd1
                = MessageDigest.getInstance("SHA-256");

            // getting the string value of msd1
            // using toString() method
            String nv = msd1.toString();

            // display the result
            System.out.println("MessageDigest : " + nv);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
MessageDigest : SHA-256 Message Digest from SUN, <initialized>

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/messagedigest . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#toString--)