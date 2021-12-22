# Java 中的 Java.net.HttpURLConnection 类

> 原文:[https://www . geesforgeks . org/Java-net-httpurconnection-class-Java/](https://www.geeksforgeeks.org/java-net-httpurlconnection-class-java/)

HttpURLConnection 类是从 [URLConnection 类](https://www.geeksforgeeks.org/reading-url-using-urlconnection-class/)直接扩展而来的抽象类。它包括其父类的所有功能以及附加的 HTTP 特定特性。HttpsURLConnection 是用于更安全的 HTTPS 协议的另一个类。
**用在哪里？**
它是 Java 开发人员与网络服务器交互的流行选择之一，安卓开发团队已经正式建议尽可能使用它。
最后，本文展示了一个交互式应用程序的简单实现，该应用程序使用微软情感 api，使用 HttpURLConnection 类的方法从图像中检索情感分数。

**施工方:**

```java
Syntax : protected HttpURLConnection(URL u):
Parameters : 
u - the url
Constructs the httpurlconnection to specified URL.

```

**方法(URLConnection 类中的方法除外):**

1.  **getResponseCode() :** 用于从服务器检索响应状态。

    ```java
    Syntax : protected int getResponseCode()
    1xx : Information
    2xx : Success
    3xx : Redirection
    4xx : Client error
    5xx : Server error

    ```

2.  **设置请求方法():**用于设置请求方法。默认为 GET。

    ```java
    Syntax :  protected void setRequestMethod(String method) 
                                    throws ProtocolException
    Parameters: 
    method : Must be any one of the following-
    GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE
    Throws :
    ProtocolException - If the method is not valid for http.

    ```

3.  **getRequestMethod() :** 返回请求方法。

    ```java
    Syntax :  protected String getRequestMethod()           

    ```

4.  **获取响应消息():**检索响应消息。

    ```java
    Syntax :  public String getResponseMessage()           
    200 - OK
    404 - NOT FOUND

    ```

5.  **getHeaderField() :** 返回第 n 个头字段，如果不存在则返回 null。它重写了 URLConnection 类的 getHeaderField 方法。

    ```java
    Syntax :  public String getHeaderField(int n)     
    Parameters: 
    n : Index of the header field.

    ```

6.  **setFixedLengthStreamingMode():**用于设置输出流上写入内容的长度，如果事先知道的话。

    ```java
    Syntax :  public void setFixedLengthStreamingMode(long n/int n) 
                                           throws IllegalStateException          

    Parameters: 
    n : Length of content to be written.
    Throws:
    IllegalStateException : If specified length of content is not written on 
    outputstream.

    ```

7.  **设置跟踪重定向():**设置是否自动重定向 3xx 响应代码请求。

    ```java
    Syntax :  public void setFollowRedirects(boolean b)           
    Parameters: 
    b : Must be true or false.

    ```

8.  **getfollowsredirections():**根据自动重定向与否返回真或假。

    ```java
    Syntax :  public static boolean getFollowRedirects()           

    ```

9.  **disconnect() :** 表示将来不太可能向服务器发出请求。

    ```java
    Syntax :  public void disconnect()           

    ```

10.  **使用代理():**如果使用代理建立连接，则返回真，否则返回假。

    ```java
    Syntax :  public boolean usingProxy()           

    ```

11.  **setChunkedStreamingMode():**当内容长度未知时使用此模式。不是创建一个固定长度的缓冲区并将其写入服务器，而是将内容分成块，然后写入。并非所有服务器都支持此模式。

    ```java
    Syntax :  public void setChunkedStreamingMode(int n) 
                                           throws IllegalStateException          
    Parameters: 
    n : length written in each chunk.
    Throws:
    IllegalStateException : If some different streaming mode is enabled.

    ```

12.  **获取权限():**获取连接到目标主机和端口所需的权限。

    ```java
    Syntax :  public Permission getPermission()           

    ```

13.  **getErrorStream() :** 如果服务器无法连接或出现错误，则获取错误流。它可以包含如何从服务器修复错误的信息。

    ```java
    Syntax :  public InputStream getErrorStream()           

    ```

14.  **设置实例允许重定向():**设置 3xx 响应代码请求是否由该实例的 httpURLconnection 自动重定向。它覆盖了更通用的设置跟随重定向
    参数。如果未指定，则实例将基于 setFollowRedirects()进行重定向。

```java
Syntax :  public void setFollowRedirects(boolean b)           
Parameters: 
b : Must be true or false.

```

*   **getInstanceFollowRedirects() :** Returns true or false depending on automatic instance redirection set or not.

    ```java
    Syntax :  public boolean getFollowRedirects()           

    ```

    参考 [URLConnection](https://www.geeksforgeeks.org/reading-url-using-urlconnection-class/) 文章中所有继承自它的方法。

    **Java 实现:**

    ```java
    // Java program to illustrate the 
    // use of HttpURLConnection
    // to retrieve the emotion score 
    // of image using Microsoft Emotion api

    import java.io.BufferedReader;
    import java.io.IOException;
    import java.io.InputStream;
    import java.io.InputStreamReader;
    import java.io.OutputStream;
    import java.net.HttpURLConnection;
    import java.net.URL;
    import org.json.simple.JSONObject;

    public class httpconclass 
    {
        public static void main(String args[]) throws IOException 
        {
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            int n = Integer.parseInt(br.readLine());
            String key = "833921b016964f95905442e0fab0c229";
            JSONObject ezm;

            while (n-- > 0) 
            {
                String image = br.readLine();
                ezm = new JSONObject();
                ezm.put("url", image);
                try 
                {

                    // url for microsoft congnitive server.
                    URL url = 
                 new URL("https://westus.api.cognitive.microsoft.com/emotion/v1.0/recognize");
                    HttpURLConnection con =
                            (HttpURLConnection) url.openConnection();

                    // set the request method and properties.
                    con.setRequestMethod("POST");
                    con.setRequestProperty("Ocp-Apim-Subscription-Key", key);
                    con.setRequestProperty("Content-Type", "application/json");
                    con.setRequestProperty("Accept", "application/json");

                    // As we know the length of our content,
                    // the following function sets the fixed 
                    // streaming mode length 83 bytes. If
                    // content length not known, comment the below line.
                    con.setFixedLengthStreamingMode(83);

                    // set the auto redirection to true
                    HttpURLConnection.setFollowRedirects(true);

                    // override the default value set by
                    // the static method setFollowRedirect above
                    con.setInstanceFollowRedirects(false);

                    // set the doOutput to true.
                    con.setDoOutput(true);

                    OutputStream out = con.getOutputStream();
                    // System.out.println(ezm.toString().getBytes().length);

                    // write on the output stream
                    out.write(ezm.toString().getBytes());
                    InputStream ip = con.getInputStream();
                    BufferedReader br1 = 
                            new BufferedReader(new InputStreamReader(ip));

                    // Print the response code
                    // and response message from server.
                    System.out.println("Response Code:" 
                                            + con.getResponseCode());
                    System.out.println("Response Message:" 
                                        + con.getResponseMessage());

                    // uncomment the following line to
                    // print the status of
                    // FollowRedirect property.
                    // System.out.println("FollowRedirects:" 
                    //              + HttpURLConnection.getFollowRedirects());

                    // to print the status of 
                    // instanceFollowRedirect property.
                    System.out.println("InstanceFollowRedirects:" 
                                    + con.getInstanceFollowRedirects());

                    // to print the 1st header field.
                    System.out.println("Header field 1:" 
                                        + con.getHeaderField(1));

                    // to print if usingProxy flag set or not.
                    System.out.println("Using proxy:" + con.usingProxy());

                    StringBuilder response = new StringBuilder();
                    String responseSingle = null;
                    while ((responseSingle = br1.readLine()) != null) 
                    {
                        response.append(responseSingle);
                    }
                    String xx = response.toString();
                    System.out.println(xx);

                } catch (Exception e) 

                {
                    System.out.println(e.getMessage());
                }

            }
        }

    }
    ```

    输出:

    ```java
    Response Code:200
    Response Message:OK
    FollowRedirects:true
    InstanceFollowRedirects:false
    Header field 1:no-cache
    Using proxy:false
    [{"faceRectangle":{"height":134,"left":62,"top":86,"width":134},"scores":{"anger":4.105452E-
    14,"contempt":1.240792E-11,"disgust":2.58925052E-11,"fear":1.82401266E-17,"happiness":1.0,
    "neutral":2.487733E-10,"sadness":6.02089044E-14,"surprise":2.665974E-12}}]

    ```

    注意:由于它是一个交互式应用程序，建议在离线平台上运行。Json 库也应该包含在项目的构建路径中，以运行这个应用程序。可以从 sourceforge.com 下载。

    **说明:**
    要测试这个程序，需要先提供要处理的图片数量，然后提供图片的 URL。您可以不设置内容长度属性，因为服务器会自动处理它，但是如果您知道长度，请每次都相应地修改它。
    在给定的源代码中，由于 contentlngth 设置为 83 字节，因此应该使用该大小的 url。示例网址-https://media . geesforgeks . org/WP-content/uploads/Brad _ Pitt . jpg

    关于微软情感 api 的详细说明，请参考[本](https://www.microsoft.com/cognitive-services/en-us/Emotion-api/documentation)页。整个过程可以简单理解如下

    1.  **使用以下网址连接到微软情感 API 的服务器:**https://westus . API . cognitive . Microsoft . com/emotion/v 1.0/recognize。
    2.  **设置触发请求的属性和方法:**在这一步中，我们设置请求对象的方法和属性。首先，我们将该方法设置为请求方法，以便在开机自检时调用。我们还设置了用户代理属性，以确保我们的请求不会因为意外的响应类型而被服务器阻止，否则这种类型在任何网络浏览器上都可以正常工作。
    3.  **激发 http get 请求:**在我们创建了 url 并创建了一个 HttpURLConnection 对象之后，我们必须实际激发一个请求。可以通过 connect()方法显式完成。每当我们试图使用任何响应消息(如 getOutputStream()等)时，它都会隐式地完成。
    4.  **写入服务器:-** 一旦我们获得服务器的输出流，我们就将图像上传到服务器进行处理。
    5.  **从服务器读取响应:**获取输入流后，我们使用 bufferedreader 从服务器输出结果。

    **参考:** [官方 Java 文档](http://docs.oracle.com/javase/7/docs/api/java/net/HttpURLConnection.html?is-external=true)

    本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。