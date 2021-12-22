# 在 Windows 系统默认浏览器中打开输入 URL 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到打开-输入-系统中的 URL-默认-windows 中的浏览器/](https://www.geeksforgeeks.org/java-program-to-open-input-url-in-system-default-browser-in-windows/)

**网址** 是你想在默认网页浏览器中显示的网址。例如，将 http://www.site.com/report.html 连线到这个输入，在浏览器的网络服务器 www.site.com 上显示 HTML 文件 report.html。

我们的问题是编写一个 java 程序，在 Windows 的系统默认浏览器中打开输入 URL。

为了打开任何网址，我们使用不同的 java 预定义文件来操作我们的桌面。

1.  [**java.awt.Desktop**](https://www.geeksforgeeks.org/java-awt-desktop-class/) **:** We use the Java. awt. Desktop class because java.awt.Desktop allows us to interact with different capabilities of our desktop. **For example,** Start the user's default browser, start the user's default mail client, etc.
2.  [**Java. net.uri**](https://www.geeksforgeeks.org/java-net-uri-class-java/) **:** Java. net.uri is used to indicate the reference of user resource identifier.

**算法:**

*   First, we create an object of our defined class, and we import it through **java.awt.desktop.**
*   In the process of creating objects, we use the **getDesktop ()** method to return the desktop instance of the current desktop context. Desktop API may not be supported on some platforms. In this case, we use the **isdesktopSupported ()** method to determine whether the current desktop is supported.

```java
  Desktop desk=Desktop.getDesktop();
```

*   Then we use the **browse ()** method, where we enter the new URL **that we want to open on the desktop ().**

```java
  desk.browse(new URI("http://xyz.com"));
```

## 爪哇

```java
// Java Program to Open Input URL in 
// System Default Browser in Windows

import java.awt.Desktop;
import java.io.*;
import java.net.URI;

class GFG {
    public static void main(String[] args)
             throws Exception
    {
        Desktop desk = Desktop.getDesktop();

        // now we enter our URL that we want to open in our
        // default browser
        desk.browse(new URI("http://xyz.com"));
    }
}
```

**输出**

```java
(Our URL "http://xyz.com" will open in our desktop default browser)
```