# Java |打印根目录

> 原文:[https://www.geeksforgeeks.org/java-print-root-directories/](https://www.geeksforgeeks.org/java-print-root-directories/)

在 Java 中，我们可以使用文件类的**列表根()**来查找所有的根目录。

```
import java.io.*;

public class GeeksforGeeks {
    public static void main(String[] args)
    {
        File[] rDirs = File.listRoots();
        for (int i = 0; i < rDirs.length; i++) 
            System.out.println(rDirs[i].toString());        
    }
}
```

输出(在有两个驱动器的窗口中)

```
C:\
D:\

```

输出(在 Linux 中)

```
/

```