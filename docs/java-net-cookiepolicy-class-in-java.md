# java 中的 java.net.CookiePolicy 类

> 原文:[https://www . geesforgeks . org/Java-net-cookiepolicy-class-in-Java/](https://www.geeksforgeeks.org/java-net-cookiepolicy-class-in-java/)

**CookiePolicy** 实现决定哪些 cookies 应该被接受，哪些应该被拒绝。提供了三种预定义的策略实现，即 ACCEPT_ALL、ACCEPT_NONE 和 ACCEPT_ORIGINAL_SERVER。

### 签名

```java
public interface CookiePolicy
```

### 菲尔茨

<figure class="table">

| 

S.NO      

 | 

田

 | 

描述

 | 

数据类型

 |
| --- | --- | --- | --- |
| 1. | 接受 _ 全部 | CookiePolicy。ACCEPT_ALL 是一个接受所有 cookies 的预定义策略。 | 静态 CookiePolicy |
| 2. | ACCEPT _ ORIGINAL _ SERVER | CookiePolicy。ACCEPT _ ORIGINAL _ SERVER 是一个预定义的策略，它只接受来自原始服务器的 cookies。 | 静态 CookiePolicy |
| 3. | ACCEPT_NONE | CookiePolicy。ACCEPT_NONE 是一个预定义的策略，不接受任何 cookies。 | 静态 CookiePolicy |

</figure>

### 方法

CookiePolicy 接口只包含一个名为 **shouldAccept(URI uri，httpookie cookie)**的方法。

### **应接受(URI uri，HttpCookie cookie)方法**

**语法:**

```java
boolean shouldAccept(URI uri, HttpCookie cookie).
```

**方法参数:**

shouldAccept()有两个 URI 和 HttpCookie 类型的参数**。**

****方法返回类型:****

 **shouldAccept()具有布尔返回类型，如果 cookie 应该被接受将返回 true，否则将返回 false。

### 定义我们自己的 cookie 策略

定义 Cookie 策略–

*   实现 Cookie 策略界面。
*   Define the shouldAccept methods of CookiePolicy and program according to our needs.** 

### 例子

**1。Java 程序设置 cookieManager cookie 策略以接受所有 cookie–**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.net.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of cookieManager
        CookieManager cookieManager = new CookieManager();
        // set cookieManager cookie policy using
        // setCookiePolicy method
        cookieManager.setCookiePolicy(CookiePolicy.ACCEPT_ALL);
        System.out.println("Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ALL");
    }
}
```

**Output**

```java
Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ALL
```

**2。Java 程序将 cookieManager cookie 策略设置为不接受 cookie–**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.net.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of cookieManager
        CookieManager cookieManager = new CookieManager();
        // set cookieManager cookie policy using
        // setCookiePolicy method
        cookieManager.setCookiePolicy(CookiePolicy.ACCEPT_NONE);
        System.out.println("Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_NONE");
    }
}
```

**Output**

```java
Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_NONE
```

**3。Java 程序设置 cookieManager cookie 策略，只接受来自原服务器的 cookie–**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.net.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of cookieManager
        CookieManager cookieManager = new CookieManager();
        // set cookieManager cookie policy using
        // setCookiePolicy method
        cookieManager.setCookiePolicy(CookiePolicy.ACCEPT_ORIGINAL_SERVER);
        System.out.println("Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ORIGINAL_SERVER");
    }
}
```

**Output**

```java
Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ORIGINAL_SERVER
```