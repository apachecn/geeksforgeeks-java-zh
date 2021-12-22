# Java 中的 KeyPairGenerator getInstance()方法，带示例

> 原文:[https://www . geeksforgeeks . org/keypairgenerator-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keypairgenerator-getinstance-method-in-java-with-examples/)

### 字符串算法

**Java . security . KeyPairGenerator**类的 **getInstance()** 方法用于返回一个为指定算法生成公钥/私钥对的 KeyPairGenerator 对象。

此方法遍历注册的安全提供程序列表，从最首选的提供程序开始。返回一个新的密钥生成器对象，该对象封装了来自支持指定算法的第一个提供程序的密钥生成器。

**语法:**

```java
public static KeyPairGenerator 
    getInstance(String algorithm)
        throws NoSuchAlgorithmException
```

**参数:**该方法以算法的标准**名称为参数。**

**返回值:**该方法返回**新的 KeyPairGenerator 对象。**

**异常:**如果没有提供程序支持指定算法的签名实现，此方法将抛出 **NoSuchAlgorithmException** 。

以下是说明 *getInstance()* 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // KeyPairGenerator
            // and getting instance
            // using getInstance() method
            KeyPairGenerator sr = KeyPairGenerator.getInstance("DSA");

            // getting the Algorithm
            String algo = sr.getAlgorithm();

            // printing the algo String
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

**示例 2:** 显示 NoSuchAlgorithmException 异常

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // KeyPairGenerator
            // and getting instance
            // using getInstance() method

            System.out.println("Trying to get"
                               + " the instance of unknown Algorithm");

            KeyPairGenerator sr = KeyPairGenerator
                                      .getInstance("TAJMAHAL");

            // getting the Algorithm
            String algo = sr.getAlgorithm();

            // printing the algo String
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
Trying to get the instance of unknown Algorithm
Exception thrown : java.security.NoSuchAlgorithmException: TAJMAHAL KeyPairGenerator not available

```

### getInstance(字符串算法，提供程序提供程序)

java.security.KeyPairGenerator 类的 **getInstance()** 方法用于返回一个为指定算法生成公钥/私钥对的 KeyPairGenerator 对象。
返回一个新的密钥生成器对象，该对象封装了来自指定提供程序对象的密钥生成器。请注意，指定的提供程序对象不必在提供程序列表中注册。

**语法:**

```java
public static KeyPairGenerator 
    getInstance(String algorithm, Provider provider)
        throws NoSuchAlgorithmException
```

**参数:**该方法将以下参数作为参数:

*   **算法**:请求的算法名称。
*   **提供者:**提供者

**返回值:**该方法返回**新的 KeyPairGenerator 对象。**

**异常:**该方法抛出以下异常:

*   **no suchalgorithm exception–**如果指定的提供程序对象中没有指定算法的 SignatureSpi 实现，则为。
*   **IllegalArgumentException–** if the provider is null.

    以下是说明 *getInstance()* 方法的示例:

    **注意:**以下程序不会在联机 IDE 上运行。

    **例 1:**

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
        {
            try {
                // creating the object of
                // KeyPairGenerator
                // and getting instance
                // using getInstance() method
                KeyPairGenerator sr = KeyPairGenerator.getInstance("DSA");

                // creating Provider object
                Provider pd = sr.getProvider();

                // getting algorithm name
                // by using getAlgorithm() mathod
                String algo = sr.getAlgorithm();

                // creating the object of KeyPairGenerator and getting instance
                // By usng getInstance() method
                KeyPairGenerator sr1 = KeyPairGenerator.getInstance(algo, pd);

                // getting the status of signature object
                KeyPair keypair = sr1.generateKeyPair();

                // printing the keypair
                System.out.println("Keypair : " + keypair);
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
    Keypair : java.security.KeyPair@12a3a380

    ```

    **示例 2:** 显示 NoSuchAlgorithmException 异常

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
        {
            try {
                // creating the object of
                // KeyPairGenerator
                // and getting instance
                // using getInstance() method
                KeyPairGenerator sr = KeyPairGenerator.getInstance("DSA");

                // creating Provider object
                Provider pd = sr.getProvider();

                // creating the object of KeyPairGenerator and getting instance
                // By usng getInstance() method
                KeyPairGenerator sr1 = KeyPairGenerator.getInstance("TAJMAHAL", pd);

                // getting the status of signature object
                KeyPair keypair = sr1.generateKeyPair();

                // printing the keypair
                System.out.println("Keypair : " + keypair);
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
    Exception thrown : java.security.NoSuchAlgorithmException: 
    no such algorithm: TAJMAHAL for provider SUN

    ```

    **示例 3:** 显示 IllegalArgumentException

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
        {
            try {
                // creating the object of
                // KeyPairGenerator
                // and getting instance
                // using getInstance() method
                KeyPairGenerator sr = KeyPairGenerator
                                          .getInstance("RSA");

                // creating Provider object
                System.out.println("Trying to assign null as a provider");
                Provider pd = null;

                // getting algorithm name
                // by using     getAlgorithm() mathod
                String algo = sr.getAlgorithm();

                // creating the object of KeyPairGenerator and getting instance
                // By usng getInstance() method
                KeyPairGenerator sr1 = KeyPairGenerator
                                           .getInstance(algo, pd);

                // getting the status of signature object
                KeyPair keypair = sr1.generateKeyPair();

                // printing the keypair
                System.out.println("Keypair : " + keypair);
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

    ```java
    Trying to assign null as a provider
    Exception thrown : java.lang.IllegalArgumentException:
     missing provider

    ```