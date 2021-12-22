# Java 中的算法参数生成器 getAlgorithm()方法，示例

> 原文:[https://www . geesforgeks . org/algorithm parameter generator-getalgorithm-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparametergenerator-getalgorithm-method-in-java-with-examples/)

**Java . security . algorithm parameter generator**类的 **getAlgorithm()** 方法用于返回与此参数生成器关联的算法的标准名称。
**语法:**

```java
public final String getAlgorithm()
```

**返回值:**该方法返回算法的字符串名称。
以下是说明 *getAlgorithm()* 方法的示例:
**示例 1:** 对于算法 *DSA*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
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
            // using getAlgorithm() method
            String algo = sr.getAlgorithm();

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

**Output:** 

```java
Algorithm : DSA
```

**示例 2:** 对于算法*差分赫尔曼*T4】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getAlgorithm() method

import java.security.*;
import java.util.*;

public class GFG1 {
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
            // using getAlgorithm() method
            String algo = sr.getAlgorithm();

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

**Output:** 

```java
Algorithm : DiffieHellman
```