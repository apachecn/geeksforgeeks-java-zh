# Java 中的 KeyStore getCertificate()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-get certificate-in-Java-method-with-examples/](https://www.geeksforgeeks.org/keystore-getcertificate-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **getCertificate()** 方法用于为请求的别名提供证书。。
**语法:**

```
public final Certificate
  getCertificate(String alias)
  throws KeyStoreException
```

**参数:**此方法接受别名的名称作为要获取其证书的参数。
**返回值:**该方法返回所请求别名的**证书**(如果存在)。
**异常:**如果不初始化这个密钥库，这个方法抛出**密钥库异常**。
**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。
以下是举例说明 **getCertificate()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getCertificate() method

import java.security.*;
import java.security.cert.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating the object of KeyStore
            // and getting instance
            // By using getInstance() method
            KeyStore sr = KeyStore.getInstance("JKS");

            // keystore password is required to access keystore
            char[] pass = ("123456").toCharArray();

            // creating and initializing object of InputStream
            InputStream is
                = new FileInputStream(
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // getting the certificate
            // using getCertificate() method
            X509Certificate cert
                = (X509Certificate)sr
                      .getCertificate("ftpkey");

            // display the result
            System.out.println("Certificate version : "
                               + cert.getVersion());
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

```
Certificate version : 3
```

**例 2:** 为*钥匙库异常*为

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getCertificate() method

import java.security.*;
import java.security.cert.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating the object of KeyStore
            // and getting instance
            // By using getInstance() method
            KeyStore sr = KeyStore.getInstance("JKS");

            // initializing keystore object
            // sr.load(is, pass);

            // getting the certificate
            // using getCertificate() method
            X509Certificate cert
                = (X509Certificate)sr
                      .getCertificate("ftpkey");

            // display the result
            System.out.println("Certificate version : "
                               + cert.getVersion());
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

```
Exception thrown :
 java.security.KeyStoreException:
 Uninitialized keystore
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # getCertificate-Java . lang . string-T4】