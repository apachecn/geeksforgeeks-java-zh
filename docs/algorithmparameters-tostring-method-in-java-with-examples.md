# Java 中的 AlgorithmParameters toString()方法，带示例

> 原文:[https://www . geesforgeks . org/algorithm parameters-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparameters-tostring-method-in-java-with-examples/)

**Java . security . algorithm parameters**类的 **toString()** 方法用于返回以特定格式描述算法参数的字符串值。

**语法:**

```java
public final String toString()
```

**返回值:**该方法返回代表算法参数的字符串值。

以下是说明 *toString()* 方法的示例:

**示例 1:** 对于算法 *DSA*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toString() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // AlgorithmParameterGenerator
            // and getting instance
            // using getInstance() method
            AlgorithmParameterGenerator
                sr
                = AlgorithmParameterGenerator
                      .getInstance("DSA");

            // initializing the AlgorithmParameterGenerator
            // with 1024 using initialize() method
            sr.init(1024);

            // generating the Parameters
            // using generateParameters() method
            AlgorithmParameters param
                = sr.generateParameters();

            // Getting String value by using
            // toString() method
            String str = param.toString();

            // display the String
            System.out.println("AlgorithmParameters : " + str);
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

```java
AlgorithmParameters :
        p:     86b9269a 3f3ef15f 76b53799 be3343de 388a6975 b693cc6d 6a6d30f5 fc3ec50a
    ea42cccd b2c015d7 7a02a4f4 a50fab90 917060be 45b0bebc bbc3a43b 627ddbee
    3d0535d0 a6358e61 92236274 aeb276e1 172ee1cb 4df47a12 052ee095 0cd0cf20
    3b0266de 3536d427 71691d4a 376489a0 2b1d1e69 7637293e fbe9692d e242c309
        q:     f220d4b5 fcc6c472 b83d321b ad261104 1feb8a77
        g:     4f4cc8bd 327f4529 e26236cf d3a66363 12fb7124 b7938ab1 f8d84871 e6a33f77
    25c2fc6d b742091c 61235e0e c71ad62b 2c49ec32 795ac8f7 3fba46ec caa5a4df
    c61d50c6 d15e6fba 813bc04d 8ab35374 5f06dc26 68d8721c 0f043dd9 04258508
    728e94d9 df517ef2 0c4c0cb1 de33c5de 7204a5ff 572b3e83 cfa1e4dd 7e849acc
```

**示例 2:** 对于算法*差分赫尔曼*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toString() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // AlgorithmParameterGenerator
            // and getting instance
            // using getInstance() method
            AlgorithmParameterGenerator
                sr
                = AlgorithmParameterGenerator
                      .getInstance("DiffieHellman");

            // initializing the AlgorithmParameterGenerator
            // with 1024 using initialize() method
            sr.init(1024);

            // generating the Parameters
            // using generateParameters() method
            AlgorithmParameters param
                = sr.generateParameters();

            // Getting String value by using
            // toString() method
            String str = param.toString();

            // display the String
            System.out.println("AlgorithmParameters : "
                               + str);
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

```java
AlgorithmParameters : SunJCE Diffie-Hellman Parameters:
p:
    d5d2f029 531fdaad 70741153 3ce13100 c94d5da4 94925f33 595a9bb9 2ea7412a
    0c571a19 4acad67c 378b2237 36924fe1 1024bd48 a86de495 b09aea4d b9ee1d36
    385b8ccd 5538827f 0fc6d045 3fb5c559 2b47ea4f acb7abb9 2c09fa79 4003b524
    4db4dd43 5a0af2e2 03180c86 68ac57b1 a34afbec b7f4e1d5 781f8d08 d6e7b687
g:
    8d00f4d0 d03fbb96 86c4978d 5b053c29 c27838ac 91bedf26 962c1f70 715d0c02
    1bf00dec 799cea78 fee27178 54f6a907 fe485b0a 4039eba3 9dd40273 b0abbd7e
    aceec123 53ffaedf 1488debf e360756b d1075cfa cebfd59e 9b2578ba 1655ee48
    c1d41778 bffac21f 810efb38 08c4abca 987c2130 2f98d5a1 0773eb3c 87fa931f
l:
    1023
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/algorithm parameters . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/security/AlgorithmParameters.html#toString--)