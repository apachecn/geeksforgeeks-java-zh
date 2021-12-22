# Java 中的 KeyFactory getProvider()方法，带示例

> 原文:[https://www . geesforgeks . org/key factory-getprovider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keyfactory-getprovider-method-in-java-with-examples/)

**java.security.KeyFactory** 类的 **getProvider()** 方法用于获取此 KeyFactory 实例使用的[提供程序的对象的名称。](https://www.geeksforgeeks.org/tag/java-provider/)

**语法:**

```java
public final Provider getProvider()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回此密钥工厂实例使用的 **[提供程序](https://www.geeksforgeeks.org/tag/java-provider/)的对象**的名称。

以下是说明 **getProvider()** 方法的示例:

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
            // creating object of keyfactory
            KeyFactory keyFactory
                = KeyFactory.getInstance("DSA");

            // getting the Provider
            // of the KeyFactory keyfactory
            // by using method getProvider()
            Provider provider
                = keyFactory.getProvider();

            // printing the provider name
            System.out.println(
                "Provider name: "
                + provider.getName());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Provider name: SUN

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

            // creating the object of KeyFactory
            KeyFactory sr
                = KeyFactory
                      .getInstance("DiffieHellman");

            // getting the Provider of the KeyFactory sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the provider name
            System.out.println(
                "Provider name: "
                + provider.getName());
        }

        catch (NoSuchAlgorithmException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Provider name: SunJCE

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keyfactory . html # getProvider–](https://docs.oracle.com/javase/9/docs/api/java/security/KeyFactory.html#getProvider--)