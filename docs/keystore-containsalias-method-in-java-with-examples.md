# KeyStore 包含 Java 中的 Alias()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-contains alias-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-containsalias-method-in-java-with-examples/)

类的 **containsAlias()** 方法用于检查所请求的 alies 是否存在。

**语法:**

```java
public final boolean containsAlias(String alias)
  throws KeyStoreException
```

**参数:**该方法将别名的名称作为要检查条目的字符串类型的参数。
**返回值:**该方法返回一个表示结果的布尔值。
**异常:**如果不初始化这个密钥库，这个方法抛出**密钥库异常**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明 **containsAlias()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.security.cert.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            KeyStore sr = KeyStore.getInstance("JKS");

            // Keystore password is require
            // to access Keystore
            char[] pass = ("123456").toCharArray();

            // creating and initializing
            // object of InputStream
            InputStream is
                = new FileInputStream(
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // checking the presence of the aliases
            // using containsAlias() method
            boolean status
                = sr.containsAlias("ftpkey");

            // display the result
            if (status)
                System.out.println("This aliases is present");
            else
                System.out.println("This aliases is absent");
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (KeyStoreException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (FileNotFoundException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (IOException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (CertificateException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
This aliases is present
```

**示例 2:** 适用于*密钥库异常*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.security.cert.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            KeyStore sr = KeyStore.getInstance("JKS");

            // initializing keystore object
            // sr.load(is, pass);

            // checking the presence of the aliases
            // using containsAlias() method
            boolean status = sr.containsAlias("gfg");

            // display the result
            if (status)
                System.out.println("This aliases is present");
            else
                System.out.println("This aliases is absent");
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (KeyStoreException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Exception thrown :
 java.security.KeyStoreException:
 Uninitialized keystore
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # contains alias-Java . lang . string-T4】