# java 中的 java.net.CacheResponse 类

> 原文:[https://www . geesforgeks . org/Java-net-cache response-class-in-Java/](https://www.geeksforgeeks.org/java-net-cacheresponse-class-in-java/)

CacheResponse 是一个抽象类，表示从响应缓存中检索资源的通道。这个类的对象提供了一个返回实体主体和相关响应头的输入流。此类从 java.lang.Object 继承方法，如 as clone、equals、finalize、 *getClass()* 、 *hashCode()* 、 *notify()* 、 *notifyAll()* 、 *toString()* 、 *wait()* 。

```
public abstract class CacheResponse  extends Object
```

**方法:** CacheResponse 类提供了如下两种方法:

1.  *格体()*格体
2.  *getHeaders（）* 方法

**方法 1:** *getBody()* 方法返回一个 InputStream，可以从中访问响应体。

**语法:**

```
public abstract InputStream getBody()  throws IOException 
```

**参数:** NA

**返回类型:**该方法将响应体作为 InputStream 返回。

**异常:**获取响应头时引发了输入/输出异常。

**实施:**

**例 1**

## Java

```
// Java Program to illustrate CacheResponse Class
// showcasing getBody() method

// Importing general class of exception
// produced by Interrupted I/Oxception
import java.io.IOException;
// Importing superclass of all IO classes
import java.io.InputStream;
// Importing Cacheresponse class from java.net package
// to create an applet
import java.net.CacheResponse;
// Importing List and Map classes
// from java.util package
import java.util.List;
import java.util.Map;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating an object of CacheResponse class
        CacheResponse cr = new CacheResponse() {
            // getHeaders() method returns response headers
            // as Map
            public Map<String, List<String> > getHeaders()
                throws IOException
            {

                return null;
            }

            // getBody() method returns response body as
            // InputStream
            public InputStream getBody() throws IOException
            {
                System.out.println(
                    "getbody() has been tested");
                return null;
            }
        };

        // Returning an InputStream from which response body
        // can be accessed
        cr.getBody();
    }
}
```

**输出**

```
getbody() has been tested
```

现在说明前面在标题中讨论的另一种方法

**方法 2:** *getHeaders()* 方法返回从响应头字段名称到字段值列表的不可变映射。

**语法:**

```
public abstract Map<String,List<String>> getHeaders()   throws IOException  
```

**参数:** NA

**返回类型:**表头作为映射的响应。

**异常:**获取响应头时引发了输入/输出异常。

**实施:**

**例 2**

T5】JavaT0T10**输出**T1