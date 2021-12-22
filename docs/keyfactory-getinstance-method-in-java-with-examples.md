# Java 中 KeyFactory getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/key factory-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keyfactory-getinstance-method-in-java-with-examples/)

### 字符串算法

**java.security.KeyFactory** 类的 **getInstance()** 方法返回一个 KeyFactory 类型的对象，该对象应用分配的 KeyFactory 算法。

**语法:**

```java
public static KeyFactory
  getInstance(String algorithm)
  throws NoSuchAlgorithmException
```

**参数:**该方法寻求**标准算法**作为参数，其实例将被创建到该关键工厂实例。

**返回值:**这个方法返回一个新的密钥工厂对象。

**异常:**如果没有提供程序支持特定算法的密钥工厂 spi 应用程序，此方法将引发以下异常:

*   **no such algorithm 异常:**.
*   **空指针异常:**如果算法为空。

以下是说明 *getInstance()* 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        try {

            // creating the object of KeyFactory
            // and getting instance
            // By using getInstance() method
            KeyFactory sr
                = KeyFactory.getInstance("DSA");

            // getting the algorithm of KeyFactory object
            String str = sr.getAlgorithm();

            // printing the status
            System.out.println("algorithm : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
algorithm : DSA

```

**示例 2:** 显示 NoSuchAlgorithmException 异常

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        try {

            // creating the object of KeyFactory
            // and getting instance
            // By using getInstance() method
            KeyFactory sr = KeyFactory.getInstance("GEEKS");

            // getting the algorithm of KeyFactory object
            String str = sr.getAlgorithm();

            // printing the status
            System.out.println("algorithm : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Exception thrown :
 java.security.NoSuchAlgorithmException:
 GEEKS KeyFactory not available

```

### getInstance(字符串算法，字符串提供程序)

**java.security.KeyFactory** 类的 **getInstance()** 方法返回一个 KeyFactory 类型的对象，该对象应用分配的 KeyFactory 算法和分配的提供程序对象。

**语法:**

```java
public static KeyFactory
  getInstance(String algorithm, String provider)
  throws NoSuchAlgorithmException
```

**参数:**此方法寻求以下参数作为参数:

*   **Algorithm** : This is the name of the algorithm used to obtain the instance.
*   **Provider** : the name of the provider to be specified.

**返回值:**该方法返回一个新的密钥工厂对象。

**异常:**此方法引发以下异常:

*   **[Nosuchalogorithm exception:** -If there is no provider available for the key factory spi application that supports a specific algorithm.
*   **非法理由例外:**【中文】和【中文】。
*   **null pointer exception:** -If the algorithm is null

以下是说明 *getInstance()* 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of KeyFactory
            // and getting instance
            // By using getInstance() method
            KeyFactory sr
                = KeyFactory.getInstance(
                    "DSA", "SUN");

            // getting the algorithm of KeyFactory object
            String str = sr.getAlgorithm();

            // printing the status
            System.out.println("algorithm : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NoSuchProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
algorithm : DSA

```

**示例 2:** 显示 NoSuchAlgorithmException 异常

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of KeyFactory
            // and getting instance
            // By using getInstance() method
            KeyFactory sr
                = KeyFactory.getInstance(
                    "RSA", "SUN");

            // getting the algorithm of KeyFactory object
            String str = sr.getAlgorithm();

            // printing the status
            System.out.println("algorithm : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NoSuchProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Exception thrown :
 java.security.NoSuchAlgorithmException:
 no such algorithm: RSA for provider SUN

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keyfactory . html # getInstance-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/security/KeyFactory.html#getInstance-java.lang.String-)