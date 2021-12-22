# Java 中的 KeyPairGenerator getProvider()方法，带示例

> 原文:[https://www . geeksforgeeks . org/keypairgenerator-get provider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-getprovider-method-in-java-with-examples/)

**Java . security . Keypairgenerator**类的 **getProvider()** 方法用于返回这个密钥对生成器对象的提供者。

**语法:**

```
public final Provider getProvider()
```

**返回值:**这个方法返回这个密钥对生成器对象的提供者。

以下是说明 **getProvider()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getProvider() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of KeyPairGenerator
            KeyPairGenerator sr = KeyPairGenerator
                                      .getInstance("RSA");

            // getting the Provider of the KeyPairGenerator sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the provider name
            System.out.println("Provider name : "
                               + provider.getName());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Provider name : SunRsaSign

```

**例 2:**

```
// Java program to demonstrate
// getProvider() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of KeyPairGenerator
            KeyPairGenerator sr = KeyPairGenerator
                                      .getInstance("DiffieHellman");

            // getting the Provider of the KeyPairGenerator sr
            // by using method getProvider()
            Provider provider = sr.getProvider();

            // printing the provider name
            System.out.println("Provider name : "
                               + provider.getName());
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Provider name : SunJCE

```