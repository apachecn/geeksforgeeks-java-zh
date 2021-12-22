# Java 中的 KeyStore isCertificateEntry()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-iscertifientry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-iscertificateentry-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **isCertificateEntry()** 方法用于检查指定的证书条目是否存在于此 KeyStore 实例中。它返回一个表示相同的布尔值。

**语法:**

```
public final boolean isCertificateEntry(String alias)
    throws KeyStoreException
```

**参数:**该方法接受**别名**的名称作为要检查其证书条目的参数。

**返回值:**该方法检查所请求别名的证书条目是否存在，并返回一个**布尔值**。

**异常:**如果密钥库还没有初始化，这个方法抛出**密钥库异常**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明**iscertifientry()**方法的示例:

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

            // checking the presence of certificate entry
            // using isCertificateEntry() method
            Boolean status
                = sr.isCertificateEntry("ftpkey");

            // display the result
            if (status)
                System.out.println(
                    "\nCertificate "
                    + "entry is present");
            else
                System.out.println(
                    "\nCertificate "
                    + "entry is not present");
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

**Output:**[![](img/51a63b4b32ed212683d92e46b0f6d128.png)](https://media.geeksforgeeks.org/wp-content/uploads/20191118165821/Output114.png)

**示例 2:** 适用于*密钥库异常*

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
            // sr.load(is, pass);

            // checking the presence of certificate entry
            // using isCertificateEntry() method
            Boolean status
                = sr.isCertificateEntry("ftpkey");

            // display the result
            if (status)
                System.out.println(
                    "\nCertificate "
                    + "entry is present");
            else
                System.out.println(
                    "\nCertificate "
                    + "entry is not present");
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

**输出:**
[![](img/4aa2628d04e2bfa1b457687955683427.png)](https://media.geeksforgeeks.org/wp-content/uploads/20191118170055/Output115.png)

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # iscertifieteentry-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/security/KeyStore.html#isCertificateEntry-java.lang.String-)