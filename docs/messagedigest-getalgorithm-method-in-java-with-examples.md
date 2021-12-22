# Java 中的 MessageDigest getAlgorithm()方法，带示例

> 原文:[https://www . geesforgeks . org/messagedigest-getalgorithm-method-in-Java-with-examples/](https://www.geeksforgeeks.org/messagedigest-getalgorithm-method-in-java-with-examples/)

**Java . security . messagedigest**类的方法 **getAlgorithm()** 用于返回与该消息摘要相关联的算法的标准名称。

**语法:**

```java
public final String getAlgorithm()
```

**返回值:**该方法返回消息摘要中使用的算法。

以下是说明 *getAlgorithm()* 方法的示例:

**例 1:**

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

            // get the name of algorithm
            // used in MessageDigest
            // using getAlgorithm() method
            String algo = msd.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm : " + algo);
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
Algorithm : MD5

```

**例 2:**

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

            // get the name of algorithm used in MessageDigest
            // using getAlgorithm() method
            String algo = msd.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm : " + algo);
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
Algorithm : SHA-256

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/messagedigest . html # getAlgorithm–](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#getAlgorithm--)