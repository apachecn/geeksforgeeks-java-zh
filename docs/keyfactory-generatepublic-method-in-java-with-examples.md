# Java 中 KeyFactory generatePublic()方法，带示例

> 原文:[https://www . geesforgeks . org/key factory-generatepublic-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keyfactory-generatepublic-method-in-java-with-examples/)

**java.security.KeyFactory** 类的 **generatePublic()** 方法用于根据提供的密钥规范(密钥资料)生成公钥对象。

**语法:**

```
public final PublicKey generatePublic(KeySpec keySpec)
                               throws InvalidKeySpecException
```

**参数:**该方法以 keySpec(私钥的规格(密钥材料))为参数。

**返回值:**该方法返回**公钥**。

**异常:**如果给定的密钥规范不适合此密钥工厂生成私钥，则此方法将引发 InvalidKeySpecException。

以下是说明 *generatePrivate()* 方法的示例

**注意:**以下程序不会在联机 IDE 上运行

**例 1:**

```
// Java program to demonstrate
// generatePublic()  method

import java.security.*;
import java.util.*;
import java.security.spec.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator.getInstance("DSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using generateKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // getting public key
            PublicKey prv = kp.getPublic();

            // getting byte data of Public key
            byte[] publicKeyBytes = prv.getEncoded();

            // creating keyspec object
            EncodedKeySpec publicKeySpec = new X509EncodedKeySpec(publicKeyBytes);

            // creating object of keyfactory
            KeyFactory keyFactory = KeyFactory.getInstance("DSA");

            // generating Public key from the provided key spec.
            // using generatePublic() method
            PublicKey publicKey = keyFactory.generatePublic(publicKeySpec);

            // printing public key
            System.out.println("public key : " + publicKey);
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
publickey : Sun DSA Public Key
    Parameters:DSA
        p:     fd7f5381 1d751229 52df4a9c 2eece4e7 f611b752 3cef4400 c31e3f80 b6512669
    455d4022 51fb593d 8d58fabf c5f5ba30 f6cb9b55 6cd7813b 801d346f f26660b7
    6b9950a5 a49f9fe8 047b1022 c24fbba9 d7feb7c6 1bf83b57 e7c6a8a6 150f04fb
    83f6d3c5 1ec30235 54135a16 9132f675 f3ae2b61 d72aeff2 2203199d d14801c7
        q:     9760508f 15230bcc b292b982 a2eb840b f0581cf5
        g:     f7e1a085 d69b3dde cbbcab5c 36b857b9 7994afbb fa3aea82 f9574c0b 3d078267
    5159578e bad4594f e6710710 8180b449 167123e8 4c281613 b7cf0932 8cc8a6e1
    3c167a8b 547c8d28 e0a3ae1e 2bb3a675 916ea37f 0bfa2135 62f1fb62 7a01243b
    cca4f1be a8519089 a883dfe1 5ae59f06 928b665e 807b5525 64014c3b fecf492a

  y:
    8f046035 5f22ccd0 56bd5d71 1f0cf770 8a420f82 4cc833ca b9585b39 6a84d4c6
    516ad382 420ec304 e69fc277 36d87647 c00e4de4 a86d9e2f abc7d75f 35bb0246
    b8a20e96 84af9676 fc9f5d2f 114b48ca 4179d9e1 81c1cbd7 d4a16948 03861f10
    64860410 345606af 5df74878 469d7661 ac486f41 58548100 fa3c6705 5be34d24

```

**示例 2:** 适用于*无效密钥特殊异常*

```
// Java program to demonstrate
// generatePublic()  method

import java.security.*;
import java.util.*;
import java.security.spec.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator.getInstance("DSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using generateKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // getting public key
            PublicKey prv = kp.getPublic();

            // getting byte data of Public key
            byte[] publicKeyBytes = prv.getEncoded();

            // creating keyspec object
            EncodedKeySpec publicKeySpec = new PKCS8EncodedKeySpec(publicKeyBytes);

            // creating object of keyfactory
            KeyFactory keyFactory = KeyFactory.getInstance("DSA");

            // generating Public key from the provided key spec.
            // using generatePublic() method
            PublicKey publicKey = keyFactory.generatePublic(publicKeySpec);

            // printing public key
            System.out.println("public key : " + publicKey);
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
Exception thrown : java.security.spec.InvalidKeySpecException: 
Inappropriate key specification

```