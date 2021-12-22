# Java 中的 Java.net.Authenticator 类

> 原文:[https://www . geesforgeks . org/Java-net-authenticator-class-Java/](https://www.geeksforgeeks.org/java-net-authenticator-class-java/)

认证器类用于需要认证才能访问某个网址的情况。一旦知道需要进行身份验证，它就会提示用户输入相同的内容，或者使用一些硬编码的用户名和密码。
要使用该类，请遵循以下步骤-

1.  创建一个扩展验证器的类。让我们将其命名为 customAuth。
2.  重写 getPasswordAuthentication()方法。此方法包含获取请求身份验证的实体的详细信息的几种方法。所有这些方法将在后面详细讨论。
3.  Set the newly created subclass as the default authenticator to be used when a http server asks for authentcation, with setDefault(Authenticator a) method of Authenticator class.

    **方法:**

    1.  **设置默认值(认证者 a) :** 设置当 HTTP 服务器需要认证时使用的认证者。

        ```java
        Syntax : public static void setDefault(Authenticator a)
                         throws SecurityException
        Parameter :
        a : authenticator to be set as default
        Throws :
        SecurityException : if security manager doesn't allow 
        setting default authenticator

        ```

    2.  **requestPasswordAuthentication() :** Asks the authenticator registered with the system for password. Returns username/password or null if not found.

        ```java
        Syntax : 
        public static PasswordAuthentication requestPasswordAuthentication(
                                                           InetAddress addr,
                                                           int port,
                                                           String protocol,
                                                           String prompt,
                                                           String scheme)
        Parameter :
        addr : Inet address of the site asking for authentication
        port : port of requesting site
        protocol : protocol used for connection
        prompt : message for the user
        scheme : authentication scheme
        Throws :
        SecurityException : if security manager doesn't allow
        setting password authentication.

        ```

        另一种重载方法，可以在 inetaddress 不可用时使用主机名的情况下使用。

        ```java
        Syntax : 
        public static PasswordAuthentication requestPasswordAuthentication(
                                                           String host,
                                                           InetAddress addr,
                                                           int port,
                                                           String protocol,
                                                           String prompt,
                                                           String scheme)
        Parameter :
        host : hostname of the site asking for authentication
        addr : Inet address of the site asking for authentication
        port : port of requesting site
        protocol : protocol used for connection
        prompt : message for the user
        scheme : authentication scheme
        Throws :
        SecurityException : if security manager doesn't allow 
        setting password authentication.

        ```

        另一种重载方法，如果请求身份验证的站点的 URL 是已知的，而不是地址和主机名，则可以使用这种方法。

        ```java
        Syntax : 
        public static PasswordAuthentication requestPasswordAuthentication(
                                                           String host,
                                                           InetAddress addr,
                                                           int port,
                                                           String protocol,
                                                           String prompt,
                                                           URL url,
                                                           String scheme)
        Parameter :
        host : hostname of the site asking for authentication
        addr : Inet address of the site asking for authentication
        port : port of requesting site
        protocol : protocol used for connection
        prompt : message for the user
        url : URL of the site requesting authentication
        scheme : authentication scheme
        Throws :
        SecurityException : if security manager doesn't allow 
        setting password authentication.

        ```

    3.  **getRequestingHost()** :返回请求身份验证的站点的主机名。

        ```java
        Syntax : protected final String getRequestingHost()

        ```

    4.  **getRequestingSite()** :返回请求认证的站点的地址。

        ```java
        Syntax : protected final InetAddress getRequestingSite()

        ```

    5.  **getRequestingPort()** :返回连接的端口。

        ```java
        Syntax : protected final int getRequestingPort()

        ```

    6.  **getRequestingProtocol()** :返回请求连接的协议。

        ```java
        Syntax : protected final String getRequestingProtocol()

        ```

    7.  **getrequestingrompt()**:返回请求者提示的消息。

        ```java
        Syntax : protected final String getRequestingPrompt()

        ```

    8.  **getRequestingScheme()** :返回请求站点的方案。

        ```java
        Syntax : protected final String getRequestingScheme()

        ```

    9.  **getpassword authentication()**:需要密码验证时调用此方法。所有子类都必须重写此方法，因为默认方法总是返回 null。

        ```java
        Syntax : protected PasswordAuthentication getPasswordAuthentication()

        ```

    10.  **getRequestingURL()** :返回请求者的 URL。

        ```java
        Syntax : protected final URL getRequestingURL()

        ```

    11.  **getRequestorType()** :如果请求者是代理或者服务器，返回。

        ```java
        Syntax : protected Authenticator.RequestorType getRequestorType()

        ```

    **Java 实现:**

    ```java
    import java.io.BufferedReader;
    import java.io.IOException;
    import java.io.InputStreamReader;
    import java.net.Authenticator;
    import java.net.InetAddress;
    import java.net.MalformedURLException;
    import java.net.PasswordAuthentication;
    import java.net.URL;

    public class javanetauthenticator 
    {
        public static void main(String[] args) 
        {

            try {

                // setDefault() method
                // Sets the authenticator that will be used by the networking code
                // when a proxy or an HTTP server asks for authentication.
                Authenticator.setDefault(new CustomAuthenticator());

                URL url = new URL("http://securedwebsite.co.in/index.htm");

                // read text returned by server
                BufferedReader in = new BufferedReader(new InputStreamReader(url.openStream()));

                String line;
                while ((line = in.readLine()) != null) {
                    System.out.println(line);
                }
                in.close();

            } catch (MalformedURLException e) {
                System.out.println("Malformed URL: " + e.getMessage());
            } catch (IOException e) {
                System.out.println("I/O Error: " + e.getMessage());
            }

        }

        public static class CustomAuthenticator extends Authenticator 
        {

            // getPasswordAuthentication() method
            // Called when password authorization is needed
            protected PasswordAuthentication getPasswordAuthentication() 
            {

                // requestPasswordAuthentication() method
                // uncomment this if default authenticator is registered with
                // the system
                // PasswordAuthentication pa=requestPasswordAuthentication
                // (inetaddr, port, protocol, prompt, scheme);

                // getRequestingPrompt() method
                String prompt = getRequestingPrompt();

                // getRequestingHost() method
                String hostname = getRequestingHost();

                // getRequestingSite() method
                InetAddress ipaddr = getRequestingSite();

                // getRequestingPort() method
                int port = getRequestingPort();

                // getRequestingProtocol() method
                String protocol = getRequestingProtocol();

                // getRequestingScheme() method
                String scheme = getRequestingScheme();

                // getRequestingURL() method
                URL u = getRequestingURL();

                // getRequestorType() method
                RequestorType rtype = getRequestorType();

                System.out.println("prompt:" + prompt);
                System.out.println("hostname:" + hostname);
                System.out.println("ipaddress:" + ipaddr);
                System.out.println("port:" + port);
                System.out.println("protocolo:" + protocol);
                System.out.println("scheme:" + scheme);
                System.out.println("URL:" + u);
                System.out.println("Requester Type:" + rtype);

                // hardcoded username and password to be used
                // this part can be replaced by an interactive code
                // to take uid and pwd form user
                String username = "admin";
                String password = "admin1";

                // Return the information (a data holder that is used by
                // Authenticator)
                return new PasswordAuthentication(username, password.toCharArray());

            }

        }
    }
    ```

    注意:这个程序只是为了解释 Authenticator 类程序的流程。程序中使用的网址是随机选择的，不代表任何实际的网址。这个程序只是展示了如何使用 Authenticator 类的方法。通过将网址更改为需要验证才能进入的服务器来测试该程序。

    **参考:** [官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/Authenticator.html)

    本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。