# 检查一个文件是否隐藏在 Java 中

> 原文:[https://www.geeksforgeeks.org/check-file-hidden-java/](https://www.geeksforgeeks.org/check-file-hidden-java/)

我们可以使用 Java 中 file 类的 is hidden()方法来检查一个文件在 Java 中是否隐藏。此方法返回一个布尔值-真或假。
 **语法:**

```java
public static boolean isHidden(Path path) throws IOException
parameters:
path – the path to the file to test.
throws:
IOException – if an I/O error occurs
SecurityException – In the case of the default provider, 
and a security manager is installed, the checkRead method
is invoked to check read access to the file.
returns:
true: if file is hidden 
false: if file is not hidden
```

隐藏的精确定义取决于平台或提供者。
**UNIX:** 如果文件的名称以句点字符('.'开头，则该文件将被隐藏).
**窗口:**如果文件不是目录，并且设置了 DOS 隐藏属性，则文件被隐藏。

根据实现的不同，isHidden()方法可能需要访问文件系统来确定文件是否被认为是隐藏的。

```java
// Java program to check if the given 
// file is hidden or not
import java.io.File;
import java.io.IOException;

public class HiddenFileCheck
{
  public static void main(String[] args)
         throws IOException, SecurityException
  {
    // Provide the complete file path here
    File file = new File("c:/myfile.txt");

    if (file.isHidden())
      System.out.println("The specified file is hidden");
    else
      System.out.println("The specified file is not hidden");
  }
}
```

本文由 **[Saket Kumar](https://www.facebook.com/saketkumar95)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。