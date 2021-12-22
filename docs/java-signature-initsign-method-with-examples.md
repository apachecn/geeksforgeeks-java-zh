# Java 签名 initSign()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-signature-initsign-method-with-examples/](https://www.geeksforgeeks.org/java-signature-initsign-method-with-examples/)

### initSign(私钥)

**java.security.Provider** 类的 **initSign()** 方法用于初始化这个对象进行签名。如果使用不同的参数再次调用此方法，它会否定此调用的效果。

**语法:**

```
public final void 
    initSign(PrivateKey privateKey) 
        throws InvalidKeyException
```

**参数:**该方法将身份的**私钥**作为将要生成签名的参数
**异常:**该方法在密钥无效的情况下抛出 **InvalidKeyException** 。

*以下是说明 initSign()方法的示例:*

**注意:**以下程序不会在联机 IDE 中运行

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// initSign() method

import java.security.*;
import java.util.*;
import sun.misc.BASE64Encoder;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // calling getKeyPair() method and assigning in keypair
            KeyPair keyPair = getKeyPair();

            // creating byte array object
            byte[] outbuff = new byte[1000];

            // data to be updated
            byte[] data = "test".getBytes("UTF8");

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // initializing the signature object with key pair
            // for signing
            // Using method initSign
            sr.initSign(keyPair.getPrivate());

            // updating the data
            sr.update(data);

            // getting the signature byte
            // of an signing operation
            // by using method sign()
            byte[] bytes = sr.sign();

            // printing the number of byte
            System.out.println("Signature:" + Arrays.toString(bytes));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (SignatureException e) {

            System.out.println("Exception thrown : " + e);
        }
    }

    // defining getKeyPair method
    private static KeyPair getKeyPair() throws NoSuchAlgorithmException
    {

        // creating the object of KeyPairGenerator
        KeyPairGenerator kpg = KeyPairGenerator.getInstance("RSA");

        // initializing with 1024
        kpg.initialize(1024);

        // returning the key pairs
        return kpg.genKeyPair();
    }
}
```

**输出:**

```
Signature:[-109, -21, 90, -114, -22,
....
....
...., 92, 1]
```

**示例 2:** 显示无效关键异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// initSign() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // data to be updated
            byte[] data = "test".getBytes("UTF8");

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // initializing the signature object with key pair
            // for signing
            // Using method initSign
            System.out.println("Trying to put null as private key ");
            sr.initSign(null);

            // updating the data
            sr.update(data);

            // getting the signature byte
            // of an signing operation
            // by using method sign()
            byte[] bytes = sr.sign();

            // printing the number of byte
            System.out.println("Signature:" + Arrays.toString(bytes));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (SignatureException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidKeyException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Trying to put null as private key 
Exception thrown : java.security.InvalidKeyException: Key must not be null
```

### initSign(私钥，SecureRandom)

**java.security.Provider** 类的 **initSign()** 方法用于初始化这个对象进行签名。如果使用不同的参数再次调用此方法，它会否定此调用的效果。

**语法:**

```
public final void 
    initSign(PrivateKey privateKey, SecureRandom random)
        throws InvalidKeyException
```

**参数:**该方法取以下参数:

*   **私钥**–将要生成签名的身份的私钥。
*   **随机**–该签名的随机来源。

**异常:**如果密钥无效，此方法抛出**invaliddkeexception**。

下面是举例说明 sign()方法的例子:

**注意:**以下程序不会在联机 IDE 中运行

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// sign() method

import java.security.*;
import java.util.*;
import sun.misc.BASE64Encoder;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // calling getKeyPair() method and assigning in keypair
            KeyPair keyPair = getKeyPair();

            // creating byte array object
            byte[] outbuff = new byte[1000];

            // data to be updated
            byte[] data = "test".getBytes("UTF8");

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // creating the object of SecureRandom
            SecureRandom sb = SecureRandom.getInstance("SHA1PRNG");

            // initializing the signature object with key pair
            // for signing
            sr.initSign(keyPair.getPrivate(), sb);

            // updating the data
            sr.update(data);

            // getting the signature byte
            // of an signing operation
            // by using method sign()
            byte[] bytes = sr.sign();

            // printing the number of byte
            System.out.println("Signature:" + Arrays.toString(bytes));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (SignatureException e) {

            System.out.println("Exception thrown : " + e);
        }
    }

    // defining getKeyPair method
    private static KeyPair getKeyPair() throws NoSuchAlgorithmException
    {

        // creating the object of KeyPairGenerator
        KeyPairGenerator kpg = KeyPairGenerator.getInstance("RSA");

        // initializing with 1024
        kpg.initialize(1024);

        // returning the key pairs
        return kpg.genKeyPair();
    }
}
```

**输出:**

```
Signature:[-121, -82, ....
....
....104, 114, -67]
```

**示例 2:** 显示无效关键异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// initSign() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating byte array object
            byte[] outbuff = new byte[1000];

            // data to be updated
            byte[] data = "test".getBytes("UTF8");

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // creating the object of SecureRandom
            SecureRandom sb = SecureRandom.getInstance("SHA1PRNG");

            // initializing the signature object with null key pair
            // for signing using initSign() method
            System.out.println("Trying to put the null as key");
            sr.initSign(null, sb);

            // updating the data
            sr.update(data);

            // getting the signature byte
            // of an signing operation
            // by using method sign()
            byte[] bytes = sr.sign();

            // printing the number of byte
            System.out.println("Signature:" + Arrays.toString(bytes));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidKeyException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Trying to put the null as key
Exception thrown : java.security.InvalidKeyException: Key must not be null
```