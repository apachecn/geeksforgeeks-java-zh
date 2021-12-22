# java 中的 java.net.ProxySelector 类

> 原文:[https://www . geesforgeks . org/Java-net-proxy selector-class-in-Java/](https://www.geeksforgeeks.org/java-net-proxyselector-class-in-java/)

代理选择器确定哪个资源必须通过代理请求，结果返回*列表<代理>*

**Proxy selector 类的方法:**

<figure class="table">

| way | describe |
| --- | --- |
| 连接失败() | This method is called when a connection cannot be established. |
| getDefault（） | This method is used to retrieve the system-wide [T0】 Proxy selector 【T1] |
|  |

</figure>

**图示:**逻辑示例代码

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate ProxySelector Class
// of java.net package
// only creating methods here

// Importing standard input output classes
import java.io.IOException;
// Importing classes from java.net package
import java.net.InetSocketAddress;
import java.net.Proxy;
import java.net.ProxySelector;
import java.net.SocketAddress;
import java.net.URI;
// Importing List and ArrayList as utility classes from
// java.util package
import java.util.ArrayList;
import java.util.List;

// Class 1
// Helper class extending ProxySelector class
public class PrivateDataProxy extends ProxySelector {

    // According to API we need to return List<Proxy>
    // even if we return only one element, so

    // Creating List class object of Proxy type
    private final List<Proxy> noProxy = new ArrayList<>();
    private final List<Proxy> proxies = new ArrayList<>();

    // Constructor of this class
    public PrivateDataProxy()
    {

        // If no proxy required to access resource
        // use Proxy.NO_PROXY
        noProxy.add(Proxy.NO_PROXY);

        // Creating  InetSocketAddress, and
        // secure.connection.com doesn't exist 443 is an
        // https port
        InetSocketAddress inetSocketAddress
            = new InetSocketAddress("secure.connection.com",
                                    443);

        // Now creating http proxy
        Proxy proxy
            = new Proxy(Proxy.Type.HTTP, inetSocketAddress);

        // Finally adding proxy into proxy list
        proxies.add(proxy);
    }

    // Method 1 of this class
    //@Override
    public List<Proxy> select(URI uri)
    {
        if (uri.getPath().startsWith("/confidential")) {
            // If URI path starts with '/confidential' then
            // use proxy server
            return proxies;
        }

        // If url don't start with '/confidential' then
        //  no need in proxy
        return noProxy;
    }

    // Method 2 of this class
    // @Override
    public void connectFailed(URI arg0, SocketAddress arg1,
                              IOException arg2)
    {
        // Properly handle connection failing
    }
}
```

**实现:**使用自定义*代理选择器*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate ProxySelector Class
// of java.net package
// Using custom ProxySelector

// Importing required classes from respective packages
import java.io.IOException;
import java.net.Proxy;
import java.net.ProxySelector;
import java.net.URISyntaxException;
import java.net.URL;
import java.util.List;

// Main class
public class ProxySelectorDemo {

    // Main driver method
    public static void main(String[] args)
        throws URISyntaxException, IOException
    {

        // Passing the string uri
        PrivateDataProxy privateDataProxy
            = new PrivateDataProxy();

        // The setting the system-wide proxy selector
        ProxySelector.setDefault(privateDataProxy);

        // Print the default value
        // using getDefault() method
        System.out.println("Default value: "
                           + ProxySelector.getDefault());

        // Display message only
        System.out.println(
            "Getting proxy for /confidential");

        // Passing the string URL
        String confidentialUrl
            = "https://www.download.com/confidential";

        // Now, calling the constructor of the URL class
        URL confidential = new URL(confidentialUrl);

        // Requiring an proxy for url
        List<Proxy> confidentialProxies
            = privateDataProxy.select(confidential.toURI());

        // Show the proxy that was selected
        System.out.println("Proxy to use : "
                           + confidentialProxies.get(0));

        // Display message only
        System.out.println(
            "Getting proxy for /non-confidential");

        // passing the string URL
        // Custom URL as input
        String nonConfidentialURL
            = "https://www.download.com/non-confidential";

        // Now, calling the constructor of the URL class
        URL nonConfidential = new URL(nonConfidentialURL);

        // Requiring an proxy for URL
        List<Proxy> nonConfidentialProxies
            = privateDataProxy.select(
                nonConfidential.toURI());

        // Display the proxy that was selected
        System.out.println("Proxy to use : "
                           + nonConfidentialProxies.get(0));
    }
}
```

**输出:**

```
Default value: entity.PrivateDataProxy@5cad8086
Getting proxy for /confidential
Proxy to use : HTTP @ secure.connection.com:443
Getting proxy for /non-confidential
Proxy to use : DIRECT
```