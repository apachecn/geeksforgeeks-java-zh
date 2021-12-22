# Java 中的 KeyStore 别名()方法，带示例

> 原文:[https://www . geesforgeks . org/keystore-alias-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-aliases-method-in-java-with-examples/)

**java.security.KeyStore** 类的**别名()**方法提供了与此 KeyStore 对象相关联的别名。

**语法:**

```
public final Enumeration aliases()
  throws KeyStoreException
```

**返回值:**该方法将与该密钥库对象相关联的所有**别名**的列表作为枚举对象返回。
**异常:**如果不初始化这个密钥库，这个方法抛出**密钥库异常**。
**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。
以下是举例说明**别名()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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

            // keystore password is require to access keystore
            char[] pass = ("123456").toCharArray();

            // creating and initializing object of InputStream
            InputStream is
                = new FileInputStream(
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // getting the list of aliases
            // using aliases() method
            Enumeration<String> e = sr.aliases();

            // display the result
            System.out.println("List of all the alias present");
            while (e.hasMoreElements()) {
                System.out.print(e.nextElement() + "");
                System.out.println();
            }
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
List of all the alias present
ftpkey
```