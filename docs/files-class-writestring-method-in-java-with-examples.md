# Java 中的文件类 writeString()方法，带示例

> 原文:[https://www . geesforgeks . org/files-class-write string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/files-class-writestring-method-in-java-with-examples/)

Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的 **writeString()** 方法用于将内容写入指定文件。

**语法:**

```
Files.writeString(path, string, options)
```

**参数:**

*   **路径**–数据类型为路径的文件路径
*   **字符串**–将在文件中以返回类型字符串输入的指定字符串。
*   **选项**–在文件中输入字符串的不同选项。比如将字符串附加到文件中，用当前字符串覆盖文件中的所有内容，等等

**返回值:**此方法不返回值。

下面是 writeString()方法的两种重载形式。

> 公共静态路径写字符串(路径路径，字符序列 csq，OpenOption…选项)抛出 IOException
> 
> 公共静态路径写字符串(路径路径，字符序列 csq，字符集 cs，OpenOption…选项)抛出 IOException

*   在第一种方法中，UTF-8 字符集用于将内容写入文件。
*   第二种方法使用指定的字符集进行相同的操作。
*   文件的打开方式在选项中指定。

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Implementation of writeString() method in Java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;

public class GFG {
    public static void main(String[] args)
    {
        // Initializing file Path with some conditions
        Path filePath
            = Paths.get("/home/mayur/", "temp", "gfg.txt");

        try {
            // Write content to file
            Files.writeString(filePath, "Hello from GFG !!",
                              StandardOpenOption.APPEND);

            // Verify file content
            String content = Files.readString(filePath);

            System.out.println(content);
        }
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
Hello from GFG ! !
```

![](img/36103e54293441218ea613ddba682f1c.png)

输出文件