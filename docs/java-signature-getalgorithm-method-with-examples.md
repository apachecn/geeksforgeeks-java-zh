# Java 签名 getAlgorithm()方法示例

> 原文:[https://www . geesforgeks . org/Java-signature-getalgorithm-method-with-examples/](https://www.geeksforgeeks.org/java-signature-getalgorithm-method-with-examples/)

**java.security.Signature** 类的 **getAlgorithm()** 方法用于返回该签名对象的算法名称。
**语法:**

```
public final String getAlgorithm()
```

**返回值:**该方法返回该签名对象的算法名称。
以下是说明 getAlgorithm()方法的示例:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr = Signature.getInstance("SHA1withDSA");

            // getting the Algorithm
            // by using method getAlgorithm()
            String algo = sr.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm: " + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Algorithm: SHA1withDSA
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating the object of Signature
            Signature sr = Signature.getInstance("NONEwithDSA");

            // getting the Algorithm
            // by using method getAlgorithm()
            String algo = sr.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm: " + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Algorithm: NONEwithDSA
```