# Java 中的 KeyStore getProvider()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-get provider-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-getprovider-method-in-java-with-examples/)

类的 **getProvider()** 方法用于获取与此密钥库实例相关联的提供程序。

**语法:**

```
public final Provider getProvider()
```

**参数:**此方法不接受任何内容作为参数。

**返回值:**此方法返回与此密钥库关联的**提供程序**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明 **getProvider()** 方法的示例:

**例 1:**

```
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
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // getting the certificate
            // using getCertificate() method
            Provider provider = sr.getProvider();

            // display the result
            System.out.println("Provider : "
                               + provider);
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

**Output:**[![](img/a7800a3dc3ed96637c5b7d5efa51f052.png)](https://media.geeksforgeeks.org/wp-content/uploads/20191118172220/Output120.png)

**示例 2:** 适用于*不加载密钥库*

```
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
                    "f:/java/private key.store");

            // getting the certificate
            // using getCertificate() method
            Provider provider = sr.getProvider();

            // display the result
            System.out.println("Provider : "
                               + provider);
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
    }
}
```

**Output:**[![](img/a7800a3dc3ed96637c5b7d5efa51f052.png)](https://media.geeksforgeeks.org/wp-content/uploads/20191118172220/Output120.png)

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # getProvider–](https://docs.oracle.com/javase/9/docs/api/java/security/KeyStore.html#getProvider--)