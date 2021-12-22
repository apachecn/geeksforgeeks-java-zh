# java 中的 Java . nio . file . path 类

> 原文:[https://www . geesforgeks . org/Java-nio-file-path-class-in-Java/](https://www.geeksforgeeks.org/java-nio-file-paths-class-in-java/)

类包含将路径字符串或 URI 转换为路径的静态方法。

**类申报:**

```
public final class Paths
extends Object
```

**方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 获取(字符串优先，字符串…更多)

 | 此方法将路径字符串或字符串序列转换为路径，这些字符串在连接时形成路径字符串。 |
| get（URI） | 此方法将给定的 URI 转换为路径对象。 |

</figure>

**1。公共静态路径获取(字符串优先，字符串…更多):**

通过将给定字符串转换为路径来返回路径。如果“more”没有指定任何字符串，那么“first”是唯一要转换的字符串。如果“more”指定了额外的字符串，那么“first”是序列的初始部分，额外的字符串将被附加到序列的“first”之后，用“/”分隔。

**参数:**

1.  首先–路径的初始部分。
2.  更多–要连接到路径的额外字符串。

**返回:**结果路径

**投掷:**

invaliddathexception–如果给定的字符串无法转换为路径

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// java.nio.file.Path.get(String first,String... more)
// method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = (Path)Paths.get("/usr", "local", "bin");

        // print Path
        System.out.println(path);
    }
}
```

**Output**

```
/usr/local/bin

```

**2 .公共静态路径获取(URI uri):** 通过将给定的 URI 转换为路径来返回路径。

**参数:**

*   uri–要转换的

**返回:**结果路径

**投掷:**

1.  IllegalArgumentException–如果 URI 的参数不合适
2.  文件系统未找到异常–如果由 URI 标识的文件系统不存在
3.  安全性例外–如果安全管理器拒绝访问文件系统

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// java.nio.file.Path.get(URI uri) method

import java.io.IOException;
import java.net.URI;
import java.net.URISyntaxException;
import java.nio.file.Paths;

public class Path {
    public static void main(String[] args)
        throws IOException, URISyntaxException
    {
        String uribase = "https://www.geeksforgeeks.org/";
        // Constructor to create a new URI
        // by parsing the string
        URI uri = new URI(uribase);

        // create object of Path
        Path path = (Path)Paths.get(uri);

        // print ParentPath
        System.out.println(path);
    }
}
```

**输出:**

```
https://www.geeksforgeeks.org/
```