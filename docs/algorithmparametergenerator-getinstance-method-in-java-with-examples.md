# Java 中的算法参数生成器 getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/algorithm parameter generator-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparametergenerator-getinstance-method-in-java-with-examples/)

### 字符串算法

**Java . security . algorithm parameter generator 类**的 **getInstance()** 方法用于返回实现指定算法的[algorithm parameter generator](https://www.geeksforgeeks.org/tag/java-algorithmparametergenerator/)类型的对象。
**语法:**

```
public static AlgorithmParameterGenerator 
  getInstance(String algorithm)
    throws NoSuchAlgorithmException
```

**参数:**该方法以算法的**标准名称**为参数。
**返回值:**该方法返回**新算法参数生成器对象。**
**异常:**此方法抛出以下异常:

*   **no suchalgorithm exception:**如果没有[提供程序](https://www.geeksforgeeks.org/tag/java-provider/)支持指定算法的算法参数生成器或 pi 实现。
*   **NullPointRexception:**如果指定的算法为空。

以下是举例说明 *getInstance()* 方法:
T3】例 1:T5】

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
            // Getting instance of
            // AlgorithmParameterGenerator
            // By using getInstance() method
            AlgorithmParameterGenerator sr
                = AlgorithmParameterGenerator
                      .getInstance("DSA");

            // getting the status of
            // AlgorithmParameterGenerator object
            String str = sr.toString();

            // printing the status
            System.out.println("Status: "
                               + str);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:** 

```
Status: java.security.AlgorithmParameterGenerator@232204a1
```