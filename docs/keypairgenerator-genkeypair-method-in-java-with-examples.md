# Java 中的 KeyPairGenerator genKeyPair()方法，带示例

> 原文:[https://www . geeksforgeeks . org/keypairgenerator-gen keypair-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-genkeypair-method-in-java-with-examples/)

**Java . security . Keypair generator**类的 **genKeyPair()** 方法用于生成密钥对。
如果这个密钥生成器没有被显式初始化，提供者特定的默认值将被用于生成的密钥的大小和其他(算法特定的)值。

这将在每次调用时生成一个新的密钥对。

**语法:**

```
public final KeyPair genKeyPair()
```

**返回值:**该方法返回生成的密钥对

以下是说明 *genKeyPair()* 方法的示例

**注意:**这些程序不会在联机 IDE 中运行。

**示例 1:** 带初始化

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator
                                       .getInstance("RSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Keypair : java.security.KeyPair@12a3a380
```

**例 2:** 无初始化

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator
                                       .getInstance("RSA");

            // getting key pairs
            // using generateKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the number of byte
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Keypair : java.security.KeyPair@12a3a380
```