# Java 中的 Java.net.JarURLConnection 类

> 原文:[https://www . geesforgeks . org/Java-net-jarurlconnection-class-Java/](https://www.geeksforgeeks.org/java-net-jarurlconnection-class-java/)

先决条件–[Java 中的 Jar 文件](https://www.geeksforgeeks.org/jar-files-java/)
**什么是 JAR 文件？**
javacchive(JAR)将所有的类捆绑在一个包中。由于归档文件是压缩的，可以通过单个 HTTP 连接下载，因此下载归档文件通常比下载单个类更快。虽然 jar 捆绑了所有的类，但是如果需要的话，它们的完全分类的名称可以用来引用单个的类。Java 提供了几种从 jar 文件中提取信息的机制。本文介绍了使用 JarURLConnection 类的方法之一。
这个类代表一个到 jar 文件、条目或目录的 URL 连接。当程序员知道 URL 引用了 jar 条目并且需要 jar 特定的功能时，可以使用它。
**Jar URL 的语法:-**
Jar URL 以指向 Jar 档案位置的通用 URL 开始。than“**jar:**”协议是前缀，最后是“**！/**“jar 档案中文件的路径在这个网址的末尾加后缀。例如，

```
jar:http://www.abcd.com/networking.jar!/com/foo/example.class
```

如果不使用路径部分，那么 URL 指向整个 jar 档案。例如，

```
jar:http://www.abcd.com/networking.jar!/
```

**构造函数:**创建到指定网址的 jar 网址连接。

```
Syntax :protected JarURLConnection(URL url)
                    throws MalformedURLException
Parameters :
url : URL to a jar archive
Throws : 
MalformedURLException: If no protocol identified or string could not be parsed.

```

**方法:**

1.  **getJarFileURL() :** 返回此连接的 jar 文件的 URL。

    ```
    Syntax :public URL getJarFileURL()
    ```

2.  **getEntryName() :** 返回此连接的条目名称，如果指向 jar 文件而不是 jar 条目文件，则返回 null。

    ```
    Syntax :public String getEntryName()
    ```

3.  **getJarFile() :** 返回这个连接的 jar 文件。

    ```
    Syntax :public abstract JarFile getJarFile()
                                throws IOException
    Throws : 
    IOException : If IO exception occurs during connection
    ```

4.  **getManifest() :** 返回此连接的清单，如果不存在，则返回 null。清单是一个特殊的文件，可以包含关于打包在 JAR 文件中的文件的信息。

    ```
    Syntax :public Manifest getManifest()
                         throws IOException
    Throws :
    IOException : If IO exception is thrown while connecting to the url.
    ```

5.  **getJarEntry() :** 返回此连接的 JAR 条目对象。java 应用程序的入口点通常是具有方法*公共静态 void main(String args[])* 的类。如果 url 指向的是 jar 文件而不是条目，则此方法返回 null。

    ```
    Syntax : public JarEntry getJarEntry()
                         throws IOException
    ```

6.  **getAttributes() :** 如果 URL 指向 jar 条目文件，则返回此连接的属性。有关属性的更多信息，请访问[官方 Java 教程](https://docs.oracle.com/javase/tutorial/deployment/jar/secman.html)。

    ```
    Syntax :public Attributes getAttributes()
                             throws IOException
    ```

7.  **getMainAttributes() :** 返回此连接的主要属性。

    ```
    Syntax :public Attributes getMainAttributes()
                                 throws IOException
    ```

8.  **getCertificates() :** 如果指向 jar 入口文件，则返回此连接的证书对象。

    ```
    Syntax : public Certificate[] getCertificates()
                                  throws IOException
    ```

下面的程序假设我们在程序中硬编码的 URL 处有一个 jar 文件。可以看到，硬编码的 URL 只指向系统上的一个文件，当通过网络使用 jar 文件时，可以通过为文件指定正确的 URL 来使用这个类。
**Java 实现:**

```
// Java program to illustrate various
// jarURLConnection class methods 
import java.io.IOException;
import java.net.JarURLConnection;
import java.net.MalformedURLException;
import java.net.URL;
import java.security.cert.Certificate;
import java.util.Arrays;
import java.util.Map.Entry;
import java.util.jar.Attributes;
import java.util.jar.JarEntry;
import java.util.jar.JarFile;
import java.util.jar.Manifest;

public class jarurltest 
{

    private final static String JAR_URL = "jar:file:/C:/Users/Rishabh/Desktop" + 
                                     "/testClass.jar!/test/testclass.class";

    public static void main(String[] args) throws Exception 
    {

        try {

            // Create a URL that refers to a jar file in the file system
            URL FileSysUrl = new URL(JAR_URL);

            // Create a jar URL connection object
            JarURLConnection jarURLConn = (JarURLConnection) FileSysUrl.openConnection();

            // getJarFileURL() method
            System.out.println("Jar file URL : " + jarURLConn.getJarFileURL());

            // getEntryName() method
            System.out.println("Entry Name : " + jarURLConn.getEntryName());

            // getJarFile() method
            JarFile jarFile = jarURLConn.getJarFile();
            System.out.println("Jar Entry: " + jarURLConn.getJarEntry());

            // getManifest() method
            Manifest manifest = jarFile.getManifest();
            System.out.println("Manifest :" + manifest.toString());

            // getJarEntry() method
            JarEntry jentry = jarURLConn.getJarEntry();
            System.out.println("Jar Entry : " + jentry.toString());

            // getAttributes() method
            Attributes attr = jarURLConn.getAttributes();
            System.out.println("Attributes : " + attr);

            // getMainAttributes() method
            Attributes attrmain = jarURLConn.getMainAttributes();
            System.out.println("\nMain Attributes details: ");

            for (Entry e : attrmain.entrySet()) 
            {
                System.out.println(e.getKey() + " " + e.getValue());
            }

            // getCertificates() method
            Certificate cert[] = jarURLConn.getCertificates();
            System.out.println("\nCertificates Info :" + Arrays.toString(cert));

        } catch (MalformedURLException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }

    }

}
```

**输出:**

```
Jar file URL : file:/C:/Users/Rishabh/Desktop/testClass.jar
Entry Name : test/testclass.class
Jar Entry: test/testclass.class
Manifest :java.util.jar.Manifest@2f1a6037
Jar Entry : test/testclass.class
Attributes : null

Main Attributes details: 
Manifest-Version 1.0
Main-Class test.testclass

Certificates Info :null

```

**相关文章:** [用 Java 处理 JAR 和 Manifest 文件](https://www.geeksforgeeks.org/working-with-jar-and-manifest-files-in-java/)

**参考文献:** [官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/JarURLConnection.html)
书籍:Java 网络编程，作者:Elliotte Rusty Harold

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。