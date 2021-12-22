# Java 中的 KeyStore getEntry()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-getentry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-getentry-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **getEntry()** 方法用于在指定别名和保护参数的帮助下获取此实例的密钥库条目。

**语法:**

```
public final KeyStore.Entry
  getEntry(String alias, 
           KeyStore.ProtectionParameter protParam)
    throws NoSuchAlgorithmException, 
           UnrecoverableEntryException, 
           KeyStoreException
```

**参数:**该方法接受以下参数作为参数。

*   **Alias** : This is the name of the keystore entry to be obtained.
*   **protparam:** Contains the password to access the keystore.

**返回值:**该方法返回所请求别名的**密钥库条目**(如果存在)。

**异常:**此方法抛出以下异常

*   **空指针异常:**吾曰空值你好啊。
*   [T0】 no suchalgorithm exception: If the algorithm is missing.
*   **If the specified password is invalid, cancel the overwrite exception:** .
*   **keystore exception:** If the keystore has not been initialized (loaded).

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明 **getCertificate()** 方法的示例:

**例 1:**

```
// Java program to demonstrate getEntry() method

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
            KeyStore sr = KeyStore.getInstance("JKS");

            // Keystore password is required
            // to access Keystore
            char[] pass = ("123456").toCharArray();

            // creating and initializing object of InputStream
            InputStream is
                = new FileInputStream(
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // creating and initializing
            // KeyStore.ProtectionParameter object
            KeyStore.ProtectionParameter entryPassword
                = new KeyStore.PasswordProtection(pass);

            // getting KeyStore.PrivateKeyEntry object
            // using getEntry() method
            KeyStore.PrivateKeyEntry print
                = (KeyStore.PrivateKeyEntry)sr
                      .getEntry("ftpkey", entryPassword);

            // display the result
            System.out.println("PrivateKey of particular entry: "
                               + print.getPrivateKey());
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
        catch (UnrecoverableEntryException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```