# 演示如何进行用户认证的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-演示-如何-用户-验证-完成/](https://www.geeksforgeeks.org/java-program-to-demonstrate-how-user-authentication-is-done/)

身份验证是验证用户或信息身份的过程。用户身份验证是在用户登录到计算机系统时验证用户身份的过程。身份验证的主要目标是允许授权用户访问计算机，并拒绝未经授权的用户访问。

**例**T0】

**逼近**

1.  A string with user name and password as user input.
2.  Check whether the user name and password match.
3.  If there is a match, users are welcome.
4.  Otherwise, display appropriate information.

下面是上述方法的实现

T3】JavaT5

```java
// Java program to check the authentication of the user

// Importing the modules
import java.util.*;

// Gfg Class
public class Gfg 
{
    // Main CLass
    public static void main(String args[])
    {
        // Declaring the username and password
        String user_name = "Geeks For Geeks";
        String password = "Geeks For Geeks";

        // Checking the validity of the input
        if(user_name.equals("Geeks For Geeks") && password.equals("Geeks For Geeks"))
        {
            // Printing Output
            System.out.println("Authentication Successful");
        }
        else
        {
            // Printing Output
            System.out.println("User name/ Password not matching");
        }
    }
}
```

T6T8**输出**T1