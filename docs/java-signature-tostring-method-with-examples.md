# Java 签名 toString()方法示例

> 原文:[https://www . geesforgeks . org/Java-signature-tostring-method-with-examples/](https://www.geeksforgeeks.org/java-signature-tostring-method-with-examples/)

**java.security.Signature** 类的 **toString()** 方法用于返回签名对象的字符串表示，提供包括对象状态和所用算法名称的信息。

**语法:**

```
public String toString()
```

**返回值:**这个方法返回这个签名对象的一个**字符串表示**。

以下是说明 *toString()* 方法的示例:

**例 1:**

```
// Java program to demonstrate
// toString() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1withDSA");

            // getting the String representation
            // by using method toString()
            String status = sr.toString();

            // printing the provider name
            System.out.println("Status : " + status);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Status : Signature object: SHA1withDSA
```

**例 2:**

```
// Java program to demonstrate
// toString() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr = Signature.getInstance("NONEwithDSA");

            // getting the String representation
            // by using method toString()
            String status = sr.toString();

            // printing the provider name
            System.out.println("Status : " + status);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Status : Signature object: NONEwithDSA
```