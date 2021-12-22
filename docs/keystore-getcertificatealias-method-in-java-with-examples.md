# Java 中 KeyStore getCertificateAlias()方法，带示例

> 原文:[https://www . geesforgeks . org/keystore-get certificate IAS-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-getcertificatealias-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **getCertificateAlias()** 方法用于获取具有指定证书的第一个 KeyStore 条目的名称。
**语法:**

```java
public final String getCertificateAlias(Certificate cert)
    throws KeyStoreException
```

**参数:**该方法接受**证书名称**作为与密钥库条目匹配的参数。
**返回值:**该方法返回具有指定证书的第一个密钥库条目的名称。
**异常:**如果不初始化这个密钥库，这个方法抛出**密钥库异常**。
**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。
以下是举例说明 **getCertificate()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getCertificate() method

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
                    "f:/java/private Key.store");

            // initializing keystore object
            sr.load(is, pass);

            // getting the certificate
            X509Certificate cert
                = (X509Certificate)sr
                      .getCertificate("ftpkey");

            // getting alias name for the keyentry
            // using getCertificateAlias() method
            String alias = sr.getCertificateAlias(cert);

            // display the result
            System.out.println("alias name for the particular entry : "
                               + alias);
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