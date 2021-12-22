# Java 中的 Jar 文件

> 原文:[https://www.geeksforgeeks.org/jar-files-java/](https://www.geeksforgeeks.org/jar-files-java/)

A [JAR (Java Archive)](https://www.geeksforgeeks.org/jar-files-java/) 是一种包文件格式，通常用于聚合许多 Java 类文件和相关的元数据和资源(文本、图像等)。)整合到一个文件中，以在 Java 平台上分发应用软件或库。
简单来说，JAR 文件是包含压缩版本的的文件。类文件、音频文件、图像文件或目录。我们可以把. jar 文件想象成一个压缩文件(。zip)是通过使用 WinZip 软件创建的。甚至，WinZip 软件可以用来提取. jar 的内容。因此，您可以将它们用于无损数据压缩、归档、解压缩和归档解包等任务。

让我们看看如何创建一个. jar 文件和相关的命令来帮助我们工作。jar 文件

**1.1 创建 JAR 文件**

**为了**创建一个. jar 文件，我们可以使用 ***jar cf 命令*** 如下所述:

**语法:**

```
jar cf jarfilename inputfiles
```

> 这里，cf 表示创建文件。例如，假设我们的包包在 C:\目录中可用，为了将它转换成一个 jar 文件，进入 pack.jar，我们可以给出如下命令:
> 
> ```
> C:\> jar cf pack.jar pack
> ```

**1。2 查看一个 JAR 文件**

现在，创建 *pack.jar* 文件。为了查看一个 JAR 文件。jar 文件，我们可以使用如下命令:

**语法:**

```
jar tf jarfilename
```

这里，tf 表示文件内容的表格视图。例如，要查看 pack.jar 文件的内容，我们可以给出命令:

```
C:/> jar tf pack.jar
```

现在，pack.jar 的内容显示如下:

```
META-INF/
META-INF/MANIFEST.MF
pack/
pack/class1.class
pack/class2.class
..
..
```

这里，类 1、类 2 等是包包中的类。前两个条目表示创建了一个清单文件并将其添加到 pack.jar 中。第三个条目表示名为 pack 的子目录，后两个条目表示目录包中的文件名。

> **注:**我们创作的时候。jar 文件，它会自动接收默认的清单文件。归档文件中只能有一个清单文件，并且它总是有路径名。

```
META-INF/MANIFEST.MF
```

该清单文件有助于指定有关打包的其他文件的信息。

**1.3** **提取一个 JAR 文件**

为了从. jar 文件中提取文件，我们可以使用下面列出的命令:

```
jar xf jarfilename
```

这里，xf 代表从 jar 文件中提取文件。例如，要提取 pack.jar 文件的内容，我们可以写:

```
C:\> jar xf pack.jar
```

这将在 C 中创建以下目录:\

```
META-INF
```

在这个目录中，我们可以看到 class1.class 和 class2.class。

```
pack 
```

**1.4 更新 JAR 文件**

JAR 工具提供了一个“u”选项，您可以通过修改现有 Jar 文件的清单或添加文件来更新其内容。添加文件的基本命令如下所示:

**语法:**

```
jar uf jar-file input-file(s)
```

这里' *uf'* 代表更新后的 jar 文件。例如，要更新 pack.jar 文件的内容，我们可以编写:

```
C:\>jar uf pack.jar
```

**1.5 运行 JAR 文件**

为了运行打包为 JAR 文件的应用程序(需要 Main 类清单头)，可以使用下面列出的命令:

**语法:**

```
C:\>java -jar pack.jar
```

**相关文章:** [用 Java 处理 JAR 和 Manifest 文件](https://www.geeksforgeeks.org/working-with-jar-and-manifest-files-in-java/)

本文由 [**尼尚·夏尔马**](https://www.facebook.com/ChippingEye2766) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。