# Java 中的 AlgorithmParameters getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/algorithm parameters-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparameters-getinstance-method-in-java-with-examples/)

### 字符串算法

**Java . security . AlgorithmParameters**类的 **getInstance()** 方法返回一个 AlgorithmParameters 类型的对象，该对象应用分配的 algorithm parameters 算法。
**语法:**

```java
public static AlgorithmParameters
  getInstance(String algorithm)
  throws NoSuchAlgorithmException
```

**参数:**该方法寻求**标准算法**作为参数。
**返回值:**该方法提供了一个新的算法参数对象。
**异常:**此方法抛出以下异常:

*   **no suchalgorithm exception:–**如果没有提供程序支持特定算法的算法参数 spi 应用程序。
*   **NullPointRexception:**–如果算法为空。

以下是举例说明 *getInstance()* 方法:
T3】例 1:T5】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of AlgorithmParameters
            // and getting instance
            // By using getInstance() method
            AlgorithmParameters sr
                = AlgorithmParameters
                      .getInstance("DES");

            // getting the status
            // of AlgorithmParameters object
            String str = sr.toString();

            // printing the status
            System.out.println("Status : " + str);
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

**Output:** 

```java
Status : null
```