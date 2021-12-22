# Java 中的 MessageDigest reset()方法，示例

> 原文:[https://www . geesforgeks . org/messagedigest-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/messagedigest-reset-method-in-java-with-examples/)

**Java . security . MessageDigest**类的 **reset()** 方法用于将当前消息摘要值重置为此 messagedigest 对象的默认消息摘要值。
**语法:**

```
public void reset()
```

**返回值:**这个方法没有什么可返回的。
以下举例说明**复位()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

import java.security.*;
import java.nio.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            byte[] barr = { 10, 20, 30, 40 };

            // creating object of MessageDigest
            MessageDigest msd1
                = MessageDigest.getInstance("MD5");

            // display the digest value before Updation
            System.out.println("MessageDigest before update : "
                               + (ByteBuffer.wrap(
                                      msd1.digest()))
                                     .getShort());

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.wrap(barr);

            // update MessageDigest value
            // using update() method
            msd1.update(bb);

            // display the digest value before Updation
            System.out.println("\nMessageDigest after update : "
                               + (ByteBuffer.wrap(
                                      msd1.digest()))
                                     .getShort());

            // reset MessageDigest value
            // using reset() method
            msd1.reset();

            // display the digest value after reset
            System.out.println("\nMessageDigest after reset : "
                               + (ByteBuffer.wrap(
                                      msd1.digest()))
                                     .getShort());
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

**Output:** 

```
MessageDigest before update : -11235

MessageDigest after update : 30835

MessageDigest after reset : -11235
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

import java.security.*;
import java.nio.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            byte[] barr = { 10, 20, 30, 40 };

            // creating object of MessageDigest
            MessageDigest msd1
                = MessageDigest.getInstance("SHA-256");

            // display the digest value before Updation
            System.out.println("MessageDigest before update : "
                               + (ByteBuffer.wrap(
                                      msd1.digest()))
                                     .getShort());

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.wrap(barr);

            // update MessageDigest value
            // using update() method
            msd1.update(bb);

            // display the digest value before Updation
            System.out.println("\nMessageDigest after update : "
                               + (ByteBuffer.wrap(
                                      msd1.digest()))
                                     .getShort());

            // reset MessageDigest value
            // using reset() method
            msd1.reset();

            // display the digest value after reset
            System.out.println("\nMessageDigest after reset : "
                               + (ByteBuffer.wrap(
                                      msd1.digest()))
                                     .getShort());
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

**Output:** 

```
MessageDigest before update : -7248

MessageDigest after update : 24403

MessageDigest after reset : -7248
```

**参考:**
[https://docs . Oracle . com/javase/9/docs/API/Java/security/messagedigest . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#reset--)