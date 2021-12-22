# Java 中 KeyFactory getAlgorithm()方法，带示例

> 原文:[https://www . geesforgeks . org/key factory-getalgorithm-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keyfactory-getalgorithm-method-in-java-with-examples/)

**java.security.KeyFactory** 类的 **getAlgorithm(** )方法用于获取与此 KeyFactory 关联的算法的名称。
**语法:**

```
public final String getAlgorithm()
```

**返回值:**此方法返回与此 KeyFactory 关联的算法的名称。
下面举例说明 *getAlgorithm()* 方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAlgorithm()  method

import java.security.*;
import java.util.*;
import java.security.spec.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of keyfactory
            KeyFactory keyFactory = KeyFactory.getInstance("DSA");

            // getting the algorithm of KeyFactory
            // using getAlgorithm() method
            String algo = keyFactory.getAlgorithm();

            // printing the algorithm
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

**Output**

```
Algorithm : DSA

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAlgorithm()  method

import java.security.*;
import java.util.*;
import java.security.spec.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of keyfactory
            KeyFactory keyFactory = KeyFactory
                                        .getInstance("DiffieHellman");

            // getting the algorithm of KeyFactory
            // using getAlgorithm() method
            String algo = keyFactory.getAlgorithm();

            // printing the algorithm
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

**Output**

```
Algorithm : DiffieHellman

```