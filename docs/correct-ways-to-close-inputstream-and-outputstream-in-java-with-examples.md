# Java 中关闭输入流和输出流的正确方法，示例

> 原文:[https://www . geeksforgeeks . org/正确的关闭方式-java 中的输入流和输出流-示例/](https://www.geeksforgeeks.org/correct-ways-to-close-inputstream-and-outputstream-in-java-with-examples/)

由于 IO 需要您处理需要正确关闭的流、通道和文件描述符，因此 Java 开发人员很难处理它们。正因为如此，很多 Java 程序员从不费心做清理工作，只做工作而忽略任何事情的懒惰真的很容易。对于从未使用 C 或 C++做过系统编程的程序员来说，这种习惯更加明显。

要释放此类作为其有限资源持有的文件描述符，并将其用于套接字连接和文件处理，关闭流是非常必要的。严重的资源泄漏也会导致文件描述符出现异常。

让我们看看一个代码，它可以在不使用任何第三方库的情况下，用 Java 将一个文件从一个目录复制到另一个目录。

## 爪哇

T0T6】

大部分代码都是正确的，甚至比许多 Java 程序员还要好。但是它有一个错误，可能会导致 Java 程序中的资源泄漏。如果输入流的 close()方法将引发异常，那么输出流将不会被关闭，即即使 fis.close()引发异常，fos.close()也不会执行。这意味着 OutputStream 保存的文件描述符永远不会释放，从而导致 Java 程序中的资源泄漏。这并不罕见。

以下是 Java 中关闭 InputStream 和 OutputStream 的正确方式:

## 【Java】

```
import java.io.*;
class Main {
    public static void main(String args[])
        throws FileNotFoundException
    {
        InputStream is = null;
        OutputStream os = null;

        try {

            is = new FileInputStream(
                "../input/fxrates.txt");
            os = new FileOutputStream(
                "../output/fxrates.txt");
            // remaining code
        }
        finally {
            try {
                if (is != null)
                    is.close();
            }
            catch (IOException e) { /* handle */
            }
            try {
                if (os != null)
                    os.close();
            }
            catch (IOException e) { /*handle */
            }
        }
    }
}
```

如果 is.close()抛出一个 IOException，那么这段代码将不会调用 os.close()，这将保证由 OutputStream 保存的文件描述符被释放。