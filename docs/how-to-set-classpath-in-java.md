# 如何在 Java 中设置类路径？

> 原文:[https://www.geeksforgeeks.org/how-to-set-classpath-in-java/](https://www.geeksforgeeks.org/how-to-set-classpath-in-java/)

类路径描述了应用程序中使用的所有必需文件可用的位置。Java 编译器和 [**JVM (Java 虚拟机)**](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 使用 CLASSPATH 定位所需文件。如果未设置类路径，Java 编译器将无法找到所需的文件，因此将引发以下错误。

```
Error: Could not find or load main class <class name> (e.g. GFG)

```

设置了 CLASSPATH 后，上述错误就解决了。

## 爪哇

```
// If the following code is run when the CLASSPATH is not
// set, it will throw the above error.

// If it is set, we get the desired result

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
          // prints GeeksForGeeks to the console
        System.out.println("GeekForGeeks!");
    }
}
```

**输出**

```
GeekForGeeks!

```