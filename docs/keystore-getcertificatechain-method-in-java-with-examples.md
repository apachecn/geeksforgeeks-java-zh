# Java 中 KeyStore getCertificateChain()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-getcertificate chain-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-getcertificatechain-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **getCertificateChain()** 方法用于为请求的别名提供证书链。。

**语法:**

```
public final Certificate[]
  getCertificateChain(String alias)
  throws KeyStoreException
```

**参数:**此方法接受一个参数**别名**，这是别名的名称。

**返回值:**此方法返回所请求别名的证书链(如果存在)。

**异常:**如果不初始化这个密钥库，这个方法抛出**密钥库异常**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明 **getCertificateChain()** 方法的示例:

**例 1:**

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

            // Keystore password is required
            // to access Keystore
            char[] pass = ("123456").toCharArray();

            // creating and initializing
            // object of InputStream
            InputStream is
                = new FileInputStream(
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // getting the certificate
            // using getCertificate() method
            Certificate[] certchain
                = sr.getCertificateChain("ftpkey");

            // display the result
            System.out.println(
                "Type of certificate at index 0 : "
                + certchain[0].getType());
        }

        catch (Exception e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```
Type of certificate at index 0 : X.509

```

**例 2:** 为*密钥库异常*

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
            KeyStore sr
                = KeyStore.getInstance("JKS");

            // initializing keystore object
            // sr.load(is, pass);

            // getting the certificate
            // using getCertificate() method
            Certificate[] certchain
                = sr.getCertificateChain("ftpkey");

            // display the result
            System.out.println(
                "Type of certifacte at index 0 : "
                + certchain[0].getType());
        }
        catch (Exception e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Exception thrown :
 java.security.KeyStoreException:
 Uninitialized keystore

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # getCertificateChain-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/security/KeyStore.html#getCertificateChain-java.lang.String-)