# Java 签名 getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-signature-getinstance-method-with-examples/](https://www.geeksforgeeks.org/java-signature-getinstance-method-with-examples/)

### 字符串算法

java.security.Provider 类的 **getInstance()** 方法用于返回实现指定签名算法的 Signature 对象。

此方法遍历注册的安全提供程序列表，从最首选的提供程序开始。返回一个新的签名对象，该对象封装了来自支持指定算法的第一个提供程序的签名响应实现。

**语法:**

```
public static Signature getInstance(String algorithm)
    throws NoSuchAlgorithmException
```

**参数:**该方法以算法的**标准名称**为参数。
**返回值:**该方法返回**新签名对象。**
**异常:**如果没有提供程序支持指定算法的签名实现，此方法将抛出**no suchalgorithm Exception**。

以下是说明 *getInstance()* 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // getting the status of signature object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
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

**Output:** 

```
Status : Signature object: SHA1WithRSA
```

**示例 2:** 显示 NoSuchAlgorithmException 异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of Signature and getting instance
            // By using getInstance() method
            System.out.println("Trying to get the instance of unknown instance");
            Signature sr = Signature.getInstance("TAJMAHAL");

            // getting the status of signature object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
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

**Output:** 

```
Trying to get the instance of unknown instance
Exception thrown : java.security.NoSuchAlgorithmException: TAJMAHAL Signature not available
```

### 签名实例(字符串算法，提供程序提供程序)

java.security.Provider 类的 **getInstance()** 方法用于返回实现指定签名算法的 Signature 对象。

返回一个新的签名对象，该对象封装了来自指定提供程序对象的签名。请注意，指定的提供程序对象不必在提供程序列表中注册。

**语法:**

```
public static Signature 
    getInstance(String algorithm, Provider provider)
        throws NoSuchAlgorithmException
```

**参数:**该方法将以下参数作为参数:

*   **算法**–请求的算法名称。
*   **提供商**–提供商

**返回值:**该方法返回**新签名对象。**

**异常:**该方法抛出以下异常:

*   **no suchalgorithm exception**–如果指定提供程序对象中没有指定算法的 SignatureSpi 实现。
*   **IllegalArgumentException**–如果提供程序为空。

以下是说明 *getInstance()* 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // creating Provider object
            Provider pd = sr.getProvider();

            // getting algorithm name
            // by using     getAlgorithm() method
            String algo = sr.getAlgorithm();

            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr1 = Signature.getInstance(algo, pd);

            // getting the status of signature object
            String str = sr1.toString();

            // printing the status
            System.out.println("Status : " + str);
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

**Output:** 

```
Status : Signature object: SHA1WithRSA
```

**示例 2:** 显示 NoSuchAlgorithmException 异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // creating Provider object
            Provider pd = sr.getProvider();

            // getting algorithm name
            // by using     getAlgorithm() method
            String algo = sr.getAlgorithm();

            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr1 = Signature.getInstance("TAJMAHAL", pd);

            // getting the status of signature object
            String str = sr1.toString();

            // printing the status
            System.out.println("Status : " + str);
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

**Output:** 

```
Exception thrown : java.security.NoSuchAlgorithmException: no such algorithm: TAJMAHAL for provider SunRsaSign
```

**示例 3:** 显示 IllegalArgumentException

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr = Signature.getInstance("SHA1WithRSA");

            // creating Provider object
            Provider pd = null;

            // getting algorithm name
            // by using     getAlgorithm() method
            String algo = sr.getAlgorithm();

            // creating the object of Signature and getting instance
            // By using getInstance() method
            Signature sr1 = Signature.getInstance(algo, pd);

            // getting the status of signature object
            String str = sr1.toString();

            // printing the status
            System.out.println("Status : " + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Exception thrown : java.lang.IllegalArgumentException: missing provider
```