# Java 中的 KeyPairGenerator initialize()方法，示例

> 原文:[https://www . geesforgeks . org/keypairgenerator-initialize-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-initialize-method-in-java-with-examples/)

### 初始化(int keysize)

**Java . security . KeyPairGenerator**的 **initialize()** 方法用于初始化 Keypairgenerator 对象以备后用。

**语法:**

```
public void initialize(int keysize)
```

**参数:**该方法寻求 int 类型的**键大小**作为参数。
**返回值:**这个方法没有什么可返回的。
**异常:**如果大于或小于指定标准的值被通过，该方法抛出**无效参数异常**。

**注意:**以下程序不会在联机 IDE 上运行。

以下是说明*初始化(int keysize)* 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // initializing with 1024
            kpg.initialize(1024);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Keypair : java.security.KeyPair@12a3a380
```

**示例 2:** 对于**无效参数异常**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // initializing with 1024
            kpg.initialize(-24);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidParameterException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Exception thrown :
 java.security.InvalidParameterException:
 RSA keys must be at least 512 bits long
```

### 初始化(整数密钥大小，安全随机)

**Java . security . KeyPairGenerator**的 **initialize()** 方法使用 SecureRandom 对象将 Keypairgenerator 初始化为特定大小，以便进一步使用。

**语法:**

```
public void initialize(int keysize,
                       SecureRandom random)
```

**参数:**该方法采用以下参数作为参数:

*   **尺寸**:即钥匙尺寸
*   **随机**:SecureRandom 类型的对象

**返回值:**该方法提供**按键生成器**的对象。
**异常:**如果大于或小于指定标准的值被通过，该方法抛出**无效参数异常**。

以下是说明*初始化()*方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // creating the object of SecureRandom
            SecureRandom se
                = SecureRandom.getInstance("SHA1PRNG");

            // initializing with 1024
            kpg.initialize(1024, se);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidParameterException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Keypair : java.security.KeyPair@4e25154f
```

**示例 2:** 对于**无效参数异常**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// genKeyPair() method

import java.security.*;
import java.util.*;

public class GFG {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating the object of KeyPairGenerator
            KeyPairGenerator kpg
                = KeyPairGenerator
                      .getInstance("RSA");

            // creating the object of SecureRandom
            SecureRandom se
                = SecureRandom.getInstance("SHA1PRNG");

            // initializing with -24
            kpg.initialize(-24, se);

            // getting key pairs
            // using genKeyPair() method
            KeyPair kp = kpg.genKeyPair();

            // printing the Keypair
            System.out.println("Keypair : " + kp);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (InvalidParameterException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Exception thrown :
 java.security.InvalidParameterException:
 RSA keys must be at least 512 bits long
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/security/keypairgenerator . html # initialize-int-Java . security . securerandom-T4】