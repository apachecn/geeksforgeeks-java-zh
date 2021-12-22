# 如何用 Java 找到并打开目录中的隐藏文件

> 原文:[https://www . geesforgeks . org/如何使用 java 找到并打开目录中的隐藏文件/](https://www.geeksforgeeks.org/how-to-find-and-open-the-hidden-files-in-a-directory-using-java/)

**先决条件:** [Java 文件处理](https://www.geeksforgeeks.org/file-handling-in-java-with-crud-operations/)

到目前为止，使用 Java 程序的操作是在没有存储在任何地方的提示符/终端上完成的。但是在软件行业，大多数程序都是为了存储从程序中获取的信息而编写的。一种方法是将提取的信息存储在文件中。

在本文中，我们将看到如何使用 Java 打开给定路径中的所有隐藏文件

<u>**什么是文件处理？**</u>
文件是用来存储各种信息的容器。通过创建一个具有唯一名称的文件，数据被永久存储在辅助内存中。文件可以由文本、图像或任何其他文档组成。

可以对文件执行的不同操作:可以对文件执行各种操作。它们是:

1.  创建新文件。
2.  打开现有文件。
3.  从文件中读取。
4.  正在写入文件。
5.  移动到文件中的特定位置。
6.  正在关闭文件。

**方法:**上述所有操作都可以在浏览目录时可见的文件上执行。但是，可能会出现目录中的文件被隐藏，数据被安全地存储在隐藏文件中的情况。但是，隐藏的文件也可以使用 java 访问。java 的 IO 包包含一个名为 *[isHidden()](https://www.geeksforgeeks.org/file-ishidden-method-in-java-with-examples/)* 的特殊方法，它的返回类型是一个布尔值，如果文件是隐藏的，则返回 true，如果文件不是隐藏的，则返回 false。除此之外，java AWT 包还包含 Desktop 类，该类拥有打开、编辑和浏览文件夹所需的所有方法。因此，打开隐藏文件的想法是使用 isHidden()方法检查文件是否隐藏，并使用 open()方法打开那些隐藏文件。

下面是上述方法的实现:

```
// Java program to find and open
// all the hidden files in a
// directory
import java.awt.Desktop;
import java.io.File;
import java.io.IOException;
import java.util.List;
import java.util.Scanner;

public class GFG {

    // Function to find and open
    // all the hidden files in a
    // directory
    public static void open(String path)
        throws IOException
    {
        // Creating the file object
        // for the path
        File file = new File(path);

        // List all the files in
        // the given path
        String[] ls = file.list();

        // Creating a file object
        // to access the files in
        // the given path
        File f;

        // Iterating through all the files
        for (int i = 0; i < ls.length; i++) {

            // Finding the path of the
            // file
            String npath = path + "/" + ls[i];

            // Accessing the file
            f = new File(npath);

            // Check whether there is any
            // hidden file
            if (f.isHidden()) {

                // Printing the hidden file
                System.out.println(
                    ls[i]
                    + "[" + npath + "]");

                // Open the hidden file using
                // the Desktop class
                Desktop d = Desktop.getDesktop();
                d.open(f);

                System.out.println(
                    ls[i] + " opened");
            }
        }
    }

    // Driver code
    public static void main(String[] args)
        throws IOException
    {

        String path = "D:";

        open(path);
    }
}
```

**注意:**上述代码无法在联机 IDE 上运行。

**输出:**这里，一个里面有一些数据的文本文件已经隐藏在“D:”目录下。上述程序的工作如下:

<video class="wp-video-shortcode" id="video-424778-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200605103408/finhHidden1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200605103408/finhHidden1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200605103408/finhHidden1.mp4)</video>