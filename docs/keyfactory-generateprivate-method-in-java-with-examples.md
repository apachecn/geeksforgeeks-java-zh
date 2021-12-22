# Java 中 KeyFactory generatePrivate()方法，带示例

> 原文:[https://www . geesforgeks . org/key factory-generateprivate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keyfactory-generateprivate-method-in-java-with-examples/)

**Java . security . keypairgenerator**类的 **generatePrivate()** 方法用于根据提供的密钥规范(密钥资料)生成私钥对象。

**语法:**

```java
public final PrivateKey generatePrivate(KeySpec keySpec)
                                 throws InvalidKeySpecException
```

**参数:**该方法以 keySpec(私钥的规格(密钥材料))为参数。

**返回值:**此方法返回私钥。

**异常:**如果给定的密钥规范不适合该密钥工厂生成私钥，该方法将抛出**invaliddeyspecexception**。

以下是说明 *generatePrivate()* 方法的示例

**注意:**以下程序不会在联机 IDE 上运行

**例 1:**

```java
// Java program to demonstrate
// generatePrivate() method

import java.security.*;
import java.util.*;
import java.security.spec.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator
                                       .getInstance("DSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using generateKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // getting public key
            PrivateKey prv = kp.getPrivate();

            // getting byte data of private key
            byte[] private KeyBytes = prv.getEncoded();

            // creating keyspec object
            EncodedKeySpec
                private KeySpec
                = new PKCS8EncodedKeySpec(private KeyBytes);

            // creating object of keyfactory
            KeyFactory keyFactory = KeyFactory.getInstance("DSA");

            // generating private key from the provided key spec.
            // using generatePrivate() method
            PrivateKey private Key = keyFactory
                                        .generatePrivate(private KeySpec);

            // printing private key
            System.out.println("PrivateKey : " + private Key);
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

```java
PrivateKey : sun.security.provider.DSAPrivateKey@fff96ed9

```

**示例 2:** 适用于*无效密钥特殊异常*

```java
// Java program to demonstrate
// generatePrivate() method

import java.security.*;
import java.util.*;
import java.security.spec.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator
                                       .getInstance("DSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using generateKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // getting public key
            PrivateKey prv = kp.getPrivate();

            // getting byte data of private key
            byte[] private KeyBytes = prv.getEncoded();

            // creating keyspec object
            EncodedKeySpec
                private KeySpec
                = new X509EncodedKeySpec(private KeyBytes);

            // creating object of keyfactory
            KeyFactory keyFactory = KeyFactory.getInstance("DSA");

            // generating private key from the provided key spec.
            // using generatePrivate() method
            PrivateKey private Key = keyFactory
                                        .generatePrivate(private KeySpec);

            // printing private key
            System.out.println("Private Key : " + private Key);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidKeySpecException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Exception thrown : java.security.spec.InvalidKeySpecException:
 Inappropriate key specification

```