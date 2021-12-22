# Java 中的 KeyPairGenerator getAlgorithm()方法，带示例

> 原文:[https://www . geesforgeks . org/keypairgenerator-getalgorithm-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-getalgorithm-method-in-java-with-examples/)

**Java . security . keypairgenerator**类的 **getAlgorithm()** 方法用于返回该密钥对生成器的算法的标准名称。有关标准算法名称的信息，请参见 Java 加密体系结构标准算法名称文档中的密钥生成器部分。
**语法:**

```
public String getAlgorithm()
```

**返回值:**该方法返回算法的标准字符串名称。
以下是举例说明 *getAlgorithm()* 方法
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator
                                       .getInstance("RSA");

            // fetching the Algorithm
            // using getAlgorithm() method
            String algo = kpg.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm : " + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Algorithm : RSA
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg = KeyPairGenerator
                                       .getInstance("DiffieHellman");

            // fetching the Algorithm
            // using getAlgorithm() method
            String algo = kpg.getAlgorithm();

            // printing the string algo
            System.out.println("Algorithm : " + algo);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Algorithm : DiffieHellman
```