# java 中的 Java . net . password authentication 类

> 原文:[https://www . geesforgeks . org/Java-net-password authentication-class-in-Java/](https://www.geeksforgeeks.org/java-net-passwordauthentication-class-in-java/)

PasswordAuthentication 类是由 java.net 包提供的，用于实现网络应用程序，当需要保存将由 Authenticator 使用的数据时，就会用到它。它保存用户名和密码。

**其构造函数的语法:**

```
PasswordAuthentication(String userName, char[] password)
```

这将为给定的用户名和密码创建新的密码身份验证对象。给定的用户密码在存储到新的密码身份验证对象之前会被克隆。

<figure class="table">

| way | Return type |
| --- | --- |
| Get user name () | Returns the user name. |
| getPassword() | Return the user password. |

</figure>

**方法详情:**

1.  getUserName():这将给出用户名并返回一个字符串值。
2.  getPassword():这将返回用户密码并返回字符数组。

**方法继承自 java.lang.Object 类:**

1.  [等于()](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)
2.  [toString()](https://www.geeksforgeeks.org/object-tostring-method-in-java/)
3.  [hashCode()](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)
4.  [克隆()](https://www.geeksforgeeks.org/clone-method-in-java-2/#:~:text=Object%20cloning%20refers%20to%20the,corresponding%20fields%20of%20this%20object.)
5.  getClass()
6.  最终确定()
7.  通知()
8.  notifyAll()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the 
// java.net.PasswordAuthentication
// Class
import java.io.*;
import java.net.PasswordAuthentication;

class GFG {

    public static void main(String args[])
    {
        GFG acc = new GFG();
        acc.proceed();
    }

    private void proceed()
    {
        // Initializing the user name
        String userName = "Geek";

        // Initializing the password - This is a char
        // array since the PasswordAuthentication
        // supports this argument
        char[] password = { 'g', 'e', 'e', 'k', 'g', 'o',
                            'r', 'g', 'e', 'e', 'k', 's' };

        PasswordAuthentication passwordAuthentication
            = new PasswordAuthentication(userName,
                                         password);
        System.out.println(
            "UserName: "
            + passwordAuthentication.getUserName());

        // The below getPassword actually returns the
        // reference to the password as per the Java API
        // documentation.
        System.out.println(
            "Password: "
            + passwordAuthentication.getPassword());

        // You can get the password in normal string
        System.out.println(
            "Password: "
            + String.copyValueOf(
                passwordAuthentication.getPassword()));
    }
}
```

**Output**

```
UserName: Geek
Password: [C@4e50df2e
Password: geekgorgeeks
```