# Java 中的 MessageDigest getProvider()方法，带示例

> 原文:[https://www . geesforgeks . org/messagedigest-getprovider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/messagedigest-getprovider-method-in-java-with-examples/)

**Java . security . messagedigest**类的方法 **getProvider()** 用于获取该消息摘要的提供者。

**语法:**

```java
public final Provider getProvider()
```

**返回值:**这个方法返回这个 MessageDigest 的提供者。

以下是说明 getProvider()方法的示例:

**示例 1:** 对于算法 *MD5*

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating object of MessageDigest
            MessageDigest msd
                = MessageDigest.getInstance("MD5");

            // getting provider used in object msd
            // using getAlgorithm() method
            Provider pro = msd.getProvider();

            // display the provider
            System.out.println("Provider : " + pro);
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

```java
Provider : SUN version 1.8

```

**示例 2:** 对于算法 *SHA-256*

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating object of MessageDigest
            MessageDigest msd
                = MessageDigest.getInstance("SHA-256");

            // getting provider used in object msd
            // using getAlgorithm() method
            Provider pro = msd.getProvider();

            // display the provider
            System.out.println("Provider : " + pro);
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

```java
Provider : SUN version 1.8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/messagedigest . html # getAlgorithm–](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#getAlgorithm--)