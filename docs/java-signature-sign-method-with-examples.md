# Java Signature sign()方法示例

> 原文:[https://www . geesforgeks . org/Java-sign-sign-method-with-examples/](https://www.geeksforgeeks.org/java-signature-sign-method-with-examples/)

### **符号(字节[]数据缓冲器，int 偏移量，int 长度)**

**java.security.Provider** 类的 **sign()** 方法用于完成签名操作，并将结果签名字节存储在提供的缓冲区数据缓冲区中，从偏移量开始。签名的格式取决于基础签名方案。
该签名对象被重置为其初始状态(在调用 initSign 方法之一后的状态)，并且可以被重用以使用相同的私钥生成进一步的签名。
**语法:**

```java
public final int sign( byte[] data, int offset, int length )
```

> **参数:**该方法将以下参数作为参数
> **数据缓冲区**–签名结果的缓冲区为字节[]数组。
> **偏移–偏移到存储签名的数据缓冲器。
> **长度**–分配给签名的数据缓冲器中的字节数。
> **返回值:**这个方法返回放入 dataBuffer 的字节数。**

****异常:**如果这个签名对象没有正确初始化或者这个签名算法不能处理提供的输入数据，这个方法抛出 **SignatureException** 。
以下是举例说明*符号()*方法:
**注意:**以下程序不会在联机 IDE 中运行
**例 1:**** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// sign() method

import java.security.*;
import java.util.*;
import sun.misc.BASE64Encoder;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // calling getKeyPair() method and assigning in
            // keypair
            KeyPair keyPair = getKeyPair();

            // creating byte array object
            byte[] outbuff = new byte[1000];

            // data to be updated
            byte[] data = "test".getBytes("UTF8");

            // creating the object of Signature
            Signature sr
                = Signature.getInstance("SHA1WithRSA");

            // initializing the signature object with key
            // pair for signing
            sr.initSign(keyPair.getPrivate());

            // updating the data
            sr.update(data);

            // getting the number of bytes
            // placed in outbuffer
            // by using method sign()
            int bytes = sr.sign(outbuff, 0, 550);

            // printing the number of byte
            System.out.println("Signature:" + bytes);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (SignatureException e) {

            System.out.println("Exception thrown : " + e);
        }
    }

    // defining getKeyPair method
    private static KeyPair getKeyPair()
        throws NoSuchAlgorithmException
    {

        // creating the object of KeyPairGenerator
        KeyPairGenerator kpg
            = KeyPairGenerator.getInstance("RSA");

        // initializing with 1024
        kpg.initialize(1024);

        // returning the key pairs
        return kpg.genKeyPair();
    }
}
```