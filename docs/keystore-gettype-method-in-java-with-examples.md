# Java 中 KeyStore getType()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-gettype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-gettype-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **getType()** 方法用于获取这个密钥库的类型。

**语法:**

```
public final String getType()
```

**参数:**此方法不接受任何内容作为参数。

**返回值:**该方法返回该密钥库的**类型**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明 **getType 的例子？()**方法:

**例 1:**

```
// Java program to demonstrate getType() method

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

            // getting the type of keystore
            // using getType?() method
            String type = sr.getType();

            // display the result
            System.out.println("Type of keystore : "
                               + type);
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

**Output:**[![](img/eafe03e066dfb0999e422dc8e0c9ee37.png)](https://media.geeksforgeeks.org/wp-content/uploads/20191118172526/Output121.png)

**示例 2:** 用于*而不加载密钥库*

```
// Java program to demonstrate getType() method

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

            // getting the type of keystore
            // using getType?() method
            String type = sr.getType();

            // display the result
            System.out.println("Type of keystore : "
                               + type);
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

**Output:**[![](img/eafe03e066dfb0999e422dc8e0c9ee37.png)](https://media.geeksforgeeks.org/wp-content/uploads/20191118172526/Output121.png)

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # getType–](https://docs.oracle.com/javase/9/docs/api/java/security/KeyStore.html#getType--)