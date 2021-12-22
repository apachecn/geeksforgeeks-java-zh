# 如何用 Java 重命名一个文件夹的所有文件？

> 原文:[https://www . geesforgeks . org/如何使用-java/](https://www.geeksforgeeks.org/how-to-rename-all-files-of-a-folder-using-java/) 重命名文件夹中的所有文件

通常，当将文件从相机文件夹传输到我们想要分析图片的工作空间时，在通过代码测试长文件时，很难处理长文件并一次又一次地将其键入。此外，文件数量可能太大，无法手动重命名每个文件。因此，自动化重命名过程变得很有必要。

示例:

```
Input : Read 50 files from the folder 
"C:\Users\Anannya Uberoi\Desktop\myfolder":
Snapshot 1 (12-05-2017 11-57).png
Snapshot 2 (12-05-2017 11-57).png
Snapshot 3 (12-05-2017 11-57).png
Snapshot 4 (12-05-2017 11-57).png   and so on.
 Output :Renamed to
1.png
2.png
3.png
4.png   and so on.

```

```
// Java program to illustrate
// how to rename Multiple Files
// together using single program
import java.io.File;
import java.io.IOException;

public class rename
{
    public static void main(String[] argv) throws IOException
    {
        // Path of folder where files are located
        String folder_path =
               "C:\\Users\\Anannya Uberoi\\Desktop\\myfolder";

        // creating new folder
        File myfolder = new File(folder_path);

        File[] file_array = myfolder.listFiles();
        for (int i = 0; i < file_array.length; i++)
        {

            if (file_array[i].isFile())
            {

                File myfile = new File(folder_path +
                         "\\" + file_array[i].getName());
                String long_file_name = file_array[i].getName();
                String[] tokens = long_file_name.split("\\s");
                String new_file_name = tokens[1];
                System.out.println(long_file_name);
                System.out.print(new_file_name);

                // file name format: "Snapshot 11 (12-05-2017 11-57).png"
                // To Shorten it to "11.png", get the substring which
                // starts after the first space character in the long
                // _file_name.
                myfile.renameTo(new File(folder_path +
                             "\\" + new_file_name + ".png"));
            }
        }
    }
}
```

输出:

```
The files get renamed successfully.

```

**注意:**需要双斜线(\\)，因为其中一个反斜杠(\)用作转义字符，另一个反斜杠(\)表示目录更改。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。