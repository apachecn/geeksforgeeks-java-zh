# Java 中的算法参数生成器 init()方法，示例

> 原文:[https://www . geesforgeks . org/algorithm parameter generator-init-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparametergenerator-init-method-in-java-with-examples/)

### 初始化(整数大小)

**Java . security . AlgorithmParameterGenerator 类**的 **init()** 方法用于初始化特定大小的 algorithm parameter generator 以供进一步使用。
**语法:**

```java
public final void init(int size)
```

**参数:**该方法以 int 类型的大小为参数。
**返回值:**此方法不返回任何内容。
以下是举例说明 *init(int size)* 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// init() method

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
            // using generateParameters() method
            AlgorithmParameters param
                = sr.generateParameters();

            // printing the keypair
            System.out.println("AlgorithmParameters : "
                               + param);
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

算法参数:
p:a 695 be 97 15 Fe 7 CDF 3f9b 4 e 5f a2 b640 cf ECC 7852 2f 3208 DC 941187 C4 be 1a 391【cfe 13145 623160769 17b 051 e 2 4fa 62871 4 aefada 2e 0 dbb 0 Fe b 0987482 9cb 9 a 290
09 e 340 DD 61 a 9 BC 49 34175131 AFE

### init(整数大小，安全随机)

**Java . security . AlgorithmParameterGenerator 类**的 **init()** 方法用于初始化特定大小的 algorithm parameter generator，以供进一步使用。
**语法:**

```java
public final void init(int size,
                       SecureRandom random)
```

**参数:**该方法以以下参数作为参数:

*   **大小**是为初始化指定的大小
*   **随机**是要指定给此算法参数生成器对象的安全对象类型

**返回值:**该方法返回**新算法参数生成器对象。**
以下是举例说明 *init()* 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// init() method

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

            // creating the object of SecureRandom
            SecureRandom se
                = SecureRandom.getInstance("SHA1PRNG");

            // initializing the AlgorithmParameterGenerator
            // with 1024 and SecureRandom object
            // using init() method
            sr.init(1024, se);

            // generating the Parameters
            // using generateParameters() method
            AlgorithmParameters param
                = sr.generateParameters();

            // printing the keypair
            System.out.println("AlgorithmParameters : "
                               + param);
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

算法参数:
p:365d af 3829d 0 11 EB 4 e 13 3bd 01 AEF 3c 25 e 6 E3 1c 6 f 993 b 5633 a 4 BF 81 ca 9680
58717 e 4 08 C3 a 9 e 7 EAD 7a 1 ff 02561 f EFD 2 EFA 0 601 c 3 f 4 c 90080 ad 0 EC 29 F3 a 9
3e 167027 c

**参考:**

*   [https://docs . Oracle . com/javase/9/docs/API/Java/security/algorithm parameter generator . html # init-int-](https://docs.oracle.com/javase/9/docs/api/java/security/AlgorithmParameterGenerator.html#init-int-)
*   [https://docs . Oracle . com/javase/9/docs/API/Java/security/algorithm parameter generator . html # init-int-Java . security . securerandom-](https://docs.oracle.com/javase/9/docs/api/java/security/AlgorithmParameterGenerator.html#init-int-java.security.SecureRandom-)