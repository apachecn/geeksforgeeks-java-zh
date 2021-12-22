# 使用 Java 下载网页

> 原文:[https://www.geeksforgeeks.org/download-web-page-using-java/](https://www.geeksforgeeks.org/download-web-page-using-java/)

阅读和下载网页的 Java 程序

> **步骤:**
> 1。创建一个 url 对象，并将 URL 作为字符串传递以下载网页。
> 网址示例=新网址(您要下载的网页的传递网址)
> 2。创建缓冲读取器对象并传递 openStream()。输入流对象中网址的方法。
> 3。创建一个 string 对象，从 stream 中逐个读取每一行。
> 4。在将要下载网页的 html 文件中写下每一行。
> 5。关闭所有对象。
> 6。如果 url 下载失败，捕获异常。

**程序:**

```
package normal;
// Java program to read and download
// webpage in html file
import java.io.*;
import java.net.URL;
import java.net.MalformedURLException;

public class download {

    public static void DownloadWebPage(String webpage)
    {
        try {

            // Create URL object
            URL url = new URL(webpage);
            BufferedReader readr = 
              new BufferedReader(new InputStreamReader(url.openStream()));

            // Enter filename in which you want to download
            BufferedWriter writer = 
              new BufferedWriter(new FileWriter("Download.html"));

            // read each line from stream till end
            String line;
            while ((line = readr.readLine()) != null) {
                writer.write(line);
            }

            readr.close();
            writer.close();
            System.out.println("Successfully Downloaded.");
        }

        // Exceptions
        catch (MalformedURLException mue) {
            System.out.println("Malformed URL Exception raised");
        }
        catch (IOException ie) {
            System.out.println("IOException raised");
        }
    }
    public static void main(String args[])
        throws IOException
    {
        String url = "https://www.geeksforgeeks.org/";
        DownloadWebPage(url);
    }
}
```

**输出:**

```
Successfully Downloaded.
```