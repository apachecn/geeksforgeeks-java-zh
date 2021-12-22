# Java 中的 AlgorithmParameters getProvider()方法，带示例

> 原文:[https://www . geesforgeks . org/algorithm parameters-getprovider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparameters-getprovider-method-in-java-with-examples/)

**Java . security . algorithm parameters**类的 **getProvider()** 方法用于返回该算法参数对象的 [provider](https://www.geeksforgeeks.org/tag/java-provider/) 。

**语法:**

```
public final Provider getProvider()
```

**返回值:**该方法返回该算法参数对象的提供者。
以下是说明 getProvider()方法的示例:
**示例 1:** 对于算法 *DSA*

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
            // creating the object of
            // AlgorithmParameters
            // and getting instance
            // using getInstance() method
            AlgorithmParameters
                sr
                = AlgorithmParameters
                      .getInstance("DSA");

            // generating the Parameters
            // using getAlgorithm() method
            Provider pro = sr.getProvider();

            // printing the string algo
            System.out.println("Provider: "
                               + pro);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:** 

```
Provider: SUN version 1.8
```