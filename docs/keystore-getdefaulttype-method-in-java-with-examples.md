# Java 中 KeyStore getDefaultType()方法，带示例

> 原文:[https://www . geesforgeks . org/keystore-getdefaulttype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-getdefaulttype-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **getDefaultType()** 方法用于提供 KeyStore 类的默认实例。

**语法:**

```
public static final String getDefaultType()
```

**参数:**该方法不取任何内容作为参数。
**返回值:**该方法返回**密钥库类**的默认实例。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明 **getDefaultType()** 方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getDefaultType() method

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

            // getting the type of default keystore
            // using getDefaultType() method
            String type
                = sr.getDefaultType();

            // display the result
            System.out.println(
                "type of default"
                + " keystore entry : "
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

**输出:**

![](img/f3000d49e3af127496edc4ac61167c52.png)

**示例 2:** *不加载密钥库*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getDefaultType() method

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
            // sr.load(is, pass);

            // getting the type of default keystore
            // using getDefaultType() method
            String type
                = sr.getDefaultType();

            // display the result
            System.out.println(
                "type of default keystore entry : "
                + type);
        }
        catch (FileNotFoundException e) {

            System.out.println("Exception thrown : " + e);
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

**输出:**

![](img/f3000d49e3af127496edc4ac61167c52.png)

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # getDefaultType–T4】