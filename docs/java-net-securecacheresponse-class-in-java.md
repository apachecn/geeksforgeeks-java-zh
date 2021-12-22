# java 中的 Java . net . securecheresponse 类

> 原文:[https://www . geeksforgeeks . org/Java-net-securecheresponse-class-in-Java/](https://www.geeksforgeeks.org/java-net-securecacheresponse-class-in-java/)

Java 中的**安全响应**类表示最初通过安全方式检索的缓存响应。

**语法:**类声明

```java
public abstract class SecureCacheResponse
extends CacheResponse
```

此类的构造函数如下

```java
SecureCacheResponse()
```

现在，这个类的方法如下:

<figure class="table">

| way | describe |
| --- | --- |
| getcipher 套件() | This method is used to return the cipher suite used on the original connection where the network resource was retrieved. |
| getlocalcertechain() | This method is used to return the certificate chain sent to the server during the original connection handshake to retrieve network resources. |
| 【getLocalPrincipal() | This method is used to return the principal sent to the server when shaking hands in the original connection of retrieving network resources. |
| getPeerPrincipal() | This method is used to return the principal of the server, which was established as part of the defined session during the original connection to retrieve network resources. |
| getserver 证书链() | This method is used to return the certificate chain of the server from the cache, which was established as part of the session defined in the original connection for retrieving network resources. |

</figure>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate SecureCacheResponse class
// Implementation and its methods

// Importing IOException and InputStream classes from
// java.io package
import java.io.IOException;
import java.io.InputStream;
// Importing java.net package for network linking
import java.net.*;
// Importing classes from java.security package to provide
// security framework to classes and interfaces
import java.security.Principal;
import java.security.cert.Certificate;
// Importing Map and List classes from java.util package
import java.util.List;
import java.util.Map;
// Importing class when peer not authenticated
import javax.net.ssl.SSLPeerUnverifiedException;

// Main class
// JavaSecureCacheResponse
public class GFG {

    // Method 1
    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Creating an final object of Principal class
        final Principal gfgPrincipal = new Principal() {
            // Method 2
            public String getName()
            {

                // As it is simply retrieving names
                return null;
            }
        };

        // Creating an object of this class
        // (SecureCacheResponse)
        final SecureCacheResponse secureCacheResponse
            = new SecureCacheResponse() {
                  // Method 3
                  // To get the name of the cipher suite
                  public String getCipherSuite()
                  {

                      // Returning the name of the cipher
                      // suite negotiated during this
                      // handshake This message will be
                      // displayed on console
                      return "Connection established";
                  }

                  // Method 4
                  // getLocalCertificateChain() method
                  public List<Certificate>
                  getLocalCertificateChain()
                  {
                      return null;
                  }

                  // Method 5
                  public List<Certificate>
                  getServerCertificateChain()
                      throws SSLPeerUnverifiedException
                  {

                      // Returning peer certificate chain
                      // associated with the ssl socket
                      return null;
                  }

                  // Method 6
                  // getPeerPrincipal() method
                  public Principal getPeerPrincipal()
                      throws SSLPeerUnverifiedException
                  {
                      return gfgPrincipal;
                  }

                  // Method 7
                  // getLocalPrincipal() method
                  public Principal getLocalPrincipal()
                  {
                      return gfgPrincipal;
                  }

                  // Method 8
                  public Map<String, List<String> >
                  getHeaders() throws IOException
                  {
                      return null;
                  }

                  // Method 9
                  public InputStream getBody()
                      throws IOException
                  {
                      return null;
                  }
              };

        // Print and display commands which are returning
        // information

        // 1\. The cipher suite in use on the original
        // connection
        System.out.println(
            "getCipherSuite() method returns: "
            + secureCacheResponse.getCipherSuite());

        // 2\. The server's principal which was recognized
        // as a part of determining the session.
        System.out.println(
            "getPeerPrincipal() method returns: "
            + secureCacheResponse.getPeerPrincipal());

        // 3\. An immutable List of Certificate representing
        // the certificate chain that was sent to the
        // server.

        // 4\. null, as no certificate chain was sent
        System.out.println(
            "getLocalCertificateChain() returns: "
            + secureCacheResponse
                  .getLocalCertificateChain());

        // 5\. Principal that was sent to the server
        // during the handshaking of the original connection
        System.out.println(
            "getLocalPrincipal() method returns: "
            + secureCacheResponse.getLocalPrincipal());
    }
}
```

**Output**

```java
getCipherSuite() method returns: Connection established
getPeerPrincipal() method returns: GFG$1@34a245ab
getLocalCertificateChain() returns: null
getLocalPrincipal() method returns: GFG$1@34a245ab

```