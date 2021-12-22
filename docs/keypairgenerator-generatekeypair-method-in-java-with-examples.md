# Java 中的 KeyPairGenerator generateKeyPair()方法，带示例

> 原文:[https://www . geesforgeks . org/keypairgenerator-generatekeypair-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-generatekeypair-method-in-java-with-examples/)

类的 **generateKeyPair()** 方法用于生成密钥对。
如果这个**密钥生成器**没有被明确初始化，提供者特定的默认值将被用于生成的密钥的大小和其他(算法特定的)值。
这将在每次调用时生成一个新的密钥对。
**语法:**

```java
public KeyPair generateKeyPair()
```

**返回值:**该方法返回生成的密钥对。
以下是举例说明 *generateKeyPair()* 方法
**注意:**以下程序不会在联机 IDE 上运行。
**示例 1:** 带初始化

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// generateKeyPair() method

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
            // using generateKeyPair() method
            KeyPair kp = kpg.generateKeyPair();

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

```java
Keypair : java.security.KeyPair@12a3a380
```

**例 2:** 无初始化

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// generateKeyPair() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator.getInstance("RSA");

            // getting key pairs
            // using generateKeyPair() method
            KeyPair kp = kpg.generateKeyPair();

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

```java
Keypair : java.security.KeyPair@12a3a380
```