# Java Signature getProvider()方法示例

> 原文:[https://www . geesforgeks . org/Java-signature-get provider-method-with-examples/](https://www.geeksforgeeks.org/java-signature-getprovider-method-with-examples/)

**java.security.Signature** 类的 **getProvider()** 方法用来返回这个签名对象的提供者。

**语法:**

```java
public final Provider getProvider()
```

**返回值:**这个方法返回这个签名对象的提供者

以下是说明 *getProvider()* 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getProvider() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr = Signature.getInstance("NONEwithDSA");

            // getting the provider
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the provider name
            System.out.println("Provider : " + provider);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Provider : SUN version 1.8

```

**例 2:**

```java
// Java program to demonstrate
// getProvider() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1withDSA");

            // getting the provider
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the provider name
            System.out.println("Provider : " + provider);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Provider : SUN version 1.8

```