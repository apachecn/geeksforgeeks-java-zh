# java 中的 Java . nio . file . SPI . file type detector 类

> 原文:[https://www . geesforgeks . org/Java-nio-file-SPI-filetypeducator-class-in-Java/](https://www.geeksforgeeks.org/java-nio-file-spi-filetypedetector-class-in-java/)

Java . nio . file . SPI . file type detector Class 扩展了 java.lang.Object Class。文件类型检测器类包含了解给定文件内容类型的方法。

**类申报:**

```
public abstract class FileTypeDetector
extends Object
```

**施工方:**

<figure class="table">

| 构造器 | 描述 |
| --- | --- |
| 受保护的文件类型检测器() | 它用于创建文件类型检测器类的新对象。 |

</figure>

**方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 示例内容类型(Path) | 它用于猜测给定文件的内容类型。 |

</figure>

**抽象字符串 probeContentType(路径路径):**用于猜测给定文件的内容类型。要知道文件的内容类型，这个方法可以检查文件名，使用文件属性，甚至检查文件中的字节。审查文件的方式完全取决于执行情况。

**参数:**

*   **路径**–要猜测内容类型的文件的路径

**返回:**给定文件的内容类型。如果无法识别文件类型，它将返回 null。

例外:

*   IOException–如果出现输入/输出错误
*   安全例外–如果安全管理器拒绝访问给定文件。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate use of probeContentType()
// method of FileTypeDetector class
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {

    public static void main(String[] args)
    {

        try {

            // create object of Path
            Path path = (Path)Paths.get("/usr", "local",
                                        "bin", "file.txt");
            // Print content type of the file present at
            // this path
            System.out.println(
                Files.probeContentType(path));
        }
        catch (IOException e) {

            e.printStackTrace();
        }
    }
}
```

**输出:**

```
text/plain
```