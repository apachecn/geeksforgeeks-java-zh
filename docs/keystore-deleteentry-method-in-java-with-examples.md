# Java 中的 KeyStore deleteEntry()方法，示例

> 原文:[https://www . geesforgeks . org/keystore-delete entry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/keystore-deleteentry-method-in-java-with-examples/)

**java.security.KeyStore** 类的 **deleteEntry(字符串别名)**方法用于删除所请求别名的条目。

**语法:**

```java
public final void deleteEntry(String alias)
  throws KeyStoreException
```

**参数:**该方法将别名的名称作为要删除条目的字符串类型的参数。

**返回值:**这个方法没有什么可返回的。

**异常:**如果不初始化这个密钥库，这个方法抛出**密钥库异常**。

**注意:**本文中的所有程序都不会在联机 IDE 上运行，因为不存在“privatekey”密钥库。您可以在系统的 Java 编译器上检查这些代码。要检查此代码，请在您的系统上创建一个密钥库“privatekey”，并设置您自己的密钥库密码来访问该密钥库。

以下是说明**删除条目()**方法的示例:

**例 1:**

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

            // creating Enumeration<String> object
            // and initializing with null
            Enumeration<String> e = null;

            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            KeyStore sr = KeyStore.getInstance("JKS");

            // keystore password is require to access keystore
            char[] pass = ("123456").toCharArray();

            // creating and initializing
            // object of InputStream
            InputStream is
                = new FileInputStream(
                    "f:/java/private key.store");

            // initializing keystore object
            sr.load(is, pass);

            // getting the list of aliases
            // using aliases() method
            e = sr.aliases();

            // display the result
            System.out.println("List of all the alias"
                               + " present before deletion");
            while (e.hasMoreElements()) {
                System.out.print(e.nextElement() + " ");
                System.out.println();
            }

            // delete the entry having alias name htttp
            // using deleteEntry method
            sr.deleteEntry("htttp");

            // getting the list of aliases
            // using aliases() method
            e = sr.aliases();

            // display the result
            System.out.println("\nList of all the alias"
                               + " present after deletion");
            while (e.hasMoreElements()) {
                System.out.print(e.nextElement() + " ");
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

**输出:**

```java
List of all the alias present before deletion
ftpkey
htttp

List of all the alias present after deletion
ftpkey

```

**例 2:** 为

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

            // creating Enumeration<String> object
            // and initializing with null
            Enumeration<String> e = null;

            // creating the object of MessageDigest
            // and getting instance
            // By using getInstance() method
            KeyStore sr = KeyStore.getInstance("JKS");

            // initializing keystore object
            // sr.load(is, pass);

            // getting the list of aliases
            // using aliases() method
            e = sr.aliases();

            // display the result
            System.out.println("List of all the alias "
                               + "present before deletion");
            while (e.hasMoreElements()) {
                System.out.print(e.nextElement() + " ");
                System.out.println();
            }

            // delete the entry having alias name htttp
            // using deleteEntry method
            sr.deleteEntry("htttp");

            // getting the list of aliases
            // using aliases() method
            e = sr.aliases();

            // display the result
            System.out.println("\nList of all the alias"
                               + " present after deletion");
            while (e.hasMoreElements()) {
                System.out.print(e.nextElement() + " ");
                System.out.println();
            }
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

```java
Exception thrown :
 java.security.KeyStoreException:
 Uninitialized keystore

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/keystore . html # delete entry-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/security/KeyStore.html#deleteEntry-java.lang.String-)