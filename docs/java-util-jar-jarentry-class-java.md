# Java 中的 Java.util.jar.JarEntry 类

> 原文:[https://www . geesforgeks . org/Java-util-jar-jarentry-class-Java/](https://www.geeksforgeeks.org/java-util-jar-jarentry-class-java/)

这个类用于表示一个 JAR 文件条目。
**施工人员:**

*   **JarEntry(JarEntry je) :** 用取自指定 JarEntry 对象的字段创建一个新的 JarEntry。
*   **JarEntry(字符串名称):**为指定的 JAR 文件条目名称创建一个新的 JarEntry。
*   **JarEntry(ZipEntry ze) :** 创建一个新的 JarEntry，其字段取自指定的 ZipEntry 对象。

**方法:**

*   **属性 getAttributes() :** 返回此条目的清单属性，如果没有，则返回空值。

    ```java
    Syntax :public Attributes getAttributes()
                             throws IOException
    Returns: the Manifest Attributes for this entry, or null if none
    ```

*   **证书[]获取证书():**返回该条目的证书对象，如果没有，则返回空值。

    ```java
    Syntax :public Certificate[] getCertificates()
    Returns: the Certificate objects for this entry, or null if none.
    ```

*   **代码设计者[] getCodeSigners() :** 返回此项的代码设计者对象，如果没有，则返回 null。

    ```java
    Syntax :public CodeSigner[] getCodeSigners()
    Returns:
    the CodeSigner objects for this entry, or null if none.
    ```

**从类 java.util.zip.ZipEntry 继承的方法** clone，getComment，getCompressedSize，getCrc，getExtra，getMethod，getName，getSize，getTime，hashCode，isDirectory，setComment，setCompressedSize，setCrc，setExtra，setMethod，setSize，setTime，toString
**从类 java.lang.Object** 继承的方法等于，finalize，getClass，notifyAll，等等，等等

注意:由于无法读取文件
**程序 1:** ，程序不会在在线 IDE 上运行

```java
//Java program demonstrating JarEntry method
import java.io.FileInputStream;
import java.io.IOException;
import java.io.PrintStream;
import java.util.jar.JarEntry;
import java.util.jar.JarInputStream;
class JarEntryDemo
{
    public static void main(String[] args) throws IOException 
    {
        FileInputStream fis = new FileInputStream("codechecker.jar");
        JarInputStream jis = new JarInputStream(fis);
        JarEntry je=jis.getNextJarEntry();

        PrintStream out = System.out;

        //illustrating getAttributes
        out.println(je.getAttributes());

        //illustrating getCodeSigner
        out.println(je.getCodeSigners());

        //illustrating getCertificates
        out.println(je.getCertificates());
    }
}
```

**程序 2:**

```java
//Java program demonstrating JarEntry method
package java.util.jar;

 import java.io.IOException;
 import java.util.zip.ZipEntry;
 import java.security.CodeSigner;
 import java.security.cert.Certificate;

 public class JarEntry extends ZipEntry
 {
    Attributes attr;
    Certificate[] certs;
    CodeSigner[] signers;

    public JarEntry(String name) 
    {
        super(name);
    }

    public JarEntry(ZipEntry ze) 
    {
        super(ze);
    }

    public JarEntry(JarEntry je)
    {
        this((ZipEntry)je);
        this.attr = je.attr;
        this.certs = je.certs;
        this.signers = je.signers;
    }

    public Attributes getAttributes() throws IOException 
    {
      return attr;
    }

    public Certificate[] getCertificates() 
    {
        return certs == null ? null : (Certificate[]) certs.clone();
    }

    public CodeSigner[] getCodeSigners() 

    {
        return signers == null ? null : (CodeSigner[]) signers.clone();
    }
}
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。