# java 中的 java.net.NetPermission 类

> 原文:[https://www . geesforgeks . org/Java-net-net permission-class-in-Java/](https://www.geeksforgeeks.org/java-net-netpermission-class-in-java/)

**网络权限**类用于允许[网络](https://www.geeksforgeeks.org/basics-computer-networking/)权限。NetPermission 类扩展了 BasicPermission 类。这是一个“命名”权限，即它包含一个名称，但不包含任何操作。

<figure class="table">

| Permission name | What permissions allow? | Risks associated with this permission |
| --- | --- | --- |
| allowHttpTrace | This permission allows the HttpTrace method to be used in HttpURLConnection | Attackers may use HTTP TRACE to access security in HTTP headers. |
| getCookieHandler | A cookie handler and get access to highly secure cookie information. |
| Get network information | This permission allows you to get the information of the local network interface. | Attackers may gain information about local hardware. |
| Get proxy selector | This permission allows the proxy selector to select the proxy to use when making a network connection. | The attacker may obtain the proxy selector and the information of the proxy host and port of the internal network [T45 | getResponseCache | This permission allows access to the local response cache. | Attackers can access local caches that may contain security information. |
| 请求密码验证 | This right grants the ability to request a password from the verifier. | Attackers can steal the password. |
| setCookieHandler | This permission allows a cookie handler to get highly secure cookie information. |
| 设置默认验证者 | This allows the verifier to be set. | Attackers can set up verifiers and obtain security information. |
| Set proxy selector | This permission allows the proxy selector to set which proxies to use when connecting to the network. | Attackers can set proxy selectors and get information about setResponseCache. | This permission allows setting the local response cache. | Attackers can access local caches that may contain security information. |
| 指定 StreamHandler | This permission allows you to specify a StreamHandler to create a URL. | Attackers can create URLs and access resources that they normally cannot access. |

</figure>

**语法:**类声明

```
public final class NetPermission
extends BasicPermission
```

该类的构造函数

<figure class="table">

| Constructor | describe |
| --- | --- |
| NetPermission (string name) | Used to create a new NetPermission object with the given name. |
| NetPermission (string name, string action) | Used to create a new NetPermission object with the given name and action. |

</figure>

从 java.security.BasicPermission 类继承的方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 等于(对象对象) | 检查两个基本权限对象是否相等 |
| 函数() | 以字符串格式返回操作 |
| hashCode() | 返回此对象的哈希值 |
| 暗示(许可权限) | 检查该对象是否暗示了给定的权限 |
| newPermissionCollection() | 返回新的权限集合对象 |

</figure>

方法继承自 java.security.Permission 类

<figure class="table">

| way | describe |
| --- | --- |
| checkGuard() | Used to implement Guard interface |
| 获取名（） | Returns the name of this permission object. |
| toString() | Returns the string representation of this permission object. |

</figure>

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Create a New allow HttpTrace Permission

// Importing required network permission classes
import java.net.NetPermission;
import java.security.Permission;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            // Creating a new allowHttpTrace permission
            Permission permission
                = new NetPermission("allowHttpTrace");

            // Printing the name of the permission using
            // getName() method
            System.out.println(permission.getName());

            // Printing the class of the permission using
            // getClass method
            System.out.println(permission.getClass());

            // Printing the hash value of this permission
            // object using hashCode() method
            System.out.println(permission.hashCode());
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the line number where the exception occurred
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
allowHttpTrace
class java.net.NetPermission
303901780
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create a New getCookieHandler Permission

// Importing required network permission classes
import java.net.NetPermission;
import java.security.Permission;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            // Creating a new getCookieHandler permission
            Permission permission
                = new NetPermission("getCookieHandler");

            // Printing the name of the permission using
            // getName() method
            System.out.println(permission.getName());

            // Printing the class of the permission using
            // getClass method
            System.out.println(permission.getClass());

            // Printing the hash value of this permission
            // object using hashCode() method
            System.out.println(permission.hashCode());
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the line number where exception occured
            // using printStackTrace() method
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
getCookieHandler
class java.net.NetPermission
1381623952
```

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Working of equals() Method

// Importing permission classes for networking
import java.net.NetPermission;
import java.security.Permission;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            // Creating a new getNetworkInformation
            // permission
            Permission Permission1 = new NetPermission(
                "getNetworkInformation");

            // Creating a new getProxySelector permission
            Permission Permission2
                = new NetPermission("getProxySelector");

            // Checking if both the given permissions are
            // equal or not using equals() method
            if (Permission1.equals(Permission2)) {

                // Print statement
                System.out.println(
                    "Both permission are equal");
            }

            // Statements differ
            else {

                // Print statement
                System.out.println(
                    "Both permission are not equal");
            }
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the line number where the exception occurred
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
Both permission are not equal
```