# 小程序和 Servlets 的区别

> 原文:[https://www . geeksforgeeks . org/applets 和 servlets 之间的区别/](https://www.geeksforgeeks.org/difference-between-applets-and-servlets/)

**先决条件:** [小服务程序](https://www.geeksforgeeks.org/introduction-java-servlets/)和[小程序](https://www.geeksforgeeks.org/java-applet-basics/)

| 小应用程序 | 小型应用程序 |
| --- | --- |
| Java applet 是用 Java 编写的小应用程序，以字节码的形式交付给用户。 | servlet 是一种 Java 编程语言类，用于扩展服务器的功能。 |
| --- | --- |
| 小程序在客户端执行。 | Servlets 在服务器端执行。 |
| --- | --- |
| 小程序用于向网络应用程序提供仅靠 HTML 无法提供的交互功能，如捕捉鼠标输入等。 | Servlets 是其他动态网络内容技术(如 PHP 和 ASP.NET)的 Java 对应物。 |
| --- | --- |
| 小程序的生命周期 init()、stop()、paint()、start()、destroy()。 | servlets 的生命周期是:- init()、service()和 destroy()。 |
| --- | --- |
| Applets 中可用的包有:-import Java . applet . *；并导入 java.awt.*。 | servlet 中可用的包有:-import javax . servlet . *；并导入 Java . servlet . http . *； |
| --- | --- |
| 小程序使用像 AWT 和 Swing 这样的用户界面类。 | 不需要用户界面。 |
| --- | --- |
| 小程序在客户端机器上更容易有风险。 | Servlets 受服务器安全保护。 |
| --- | --- |
| 小程序在客户端机器上执行时会利用更多的网络带宽。 | Servlets 在服务器上执行，因此需要更少的带宽。 |
| --- | --- |
| 需要 java 兼容的浏览器来执行。 | 它接受来自浏览器的输入，并以网页、Javascript 对象、小程序等形式生成响应。 |
| --- | --- |

**示例**:

*   创建“你好世界”小程序。

    ```java
    // A Hello World Applet
    // Save file as HelloWorld.java

    import java.applet.Applet;
    import java.awt.Graphics;

    // HelloWorld class extends Applet
    public class HelloWorld extends Applet {

        // Overriding paint() method
        @Override
        public void paint(Graphics g)
        {
            g.drawString("Hello World", 20, 20);
        }
    }
    ```

*   创建“你好世界”Servlet。

    ```java
    // Import required java libraries
    import java.io.*;
    import javax.servlet.*;
    import javax.servlet.http.*;

    // Extend HttpServlet class
    public class HelloWorld extends HttpServlet {

        private String message;

        public void init() throws ServletException
        {
            // Do required initialization
            message = "Hello World";
        }

        public void doGet(HttpServletRequest request,
                          HttpServletResponse response)
            throws ServletException, IOException
        {

            // Set response content type
            response.setContentType("text/html");

            // Actual logic goes here.
            PrintWriter out = response.getWriter();
            out.println("<h1>" + message + "</h1>");
        }

        public void destroy()
        {
            // do nothing.
        }
    }
    ```