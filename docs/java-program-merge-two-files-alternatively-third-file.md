# Java 程序将两个文件交替合并成第三个文件

> 原文:[https://www . geesforgeks . org/Java-program-merge-two-file-alternative-third-file/](https://www.geeksforgeeks.org/java-program-merge-two-files-alternatively-third-file/)

**先决条件:** [打印作者](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)[缓冲器](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)

假设给定的两个文件是 file1.txt 和 file2.txt。我们的任务是将这两个文件合并成第三个文件，比如 file3.txt，但是合并应该逐行交替进行。以下是交替合并的步骤。

1.  Create a PrintWriter object for the file 3.txt
2.  为文件 1.txt 打开 buffere 阅读器
3.  为文件 2.txt 打开 buffere 阅读器
4.  Run a loop to copy every line of file 1.txt, and then copy file 2.txt to file 3.txt.
5.  Refresh the PrintWriter stream and close the resource.

要成功运行以下程序，文件 1.txt 和文件 2.txt 必须存在于同一个文件夹中，或者为它们提供完整路径。

```
// Java program to merge two 
// files  into third file alternatively

import java.io.*;

public class FileMerge 
{
    public static void main(String[] args) throws IOException 
    {
        // PrintWriter object for file3.txt
        PrintWriter pw = new PrintWriter("file3.txt");

        // BufferedReader object for file1.txt
        BufferedReader br1 = new BufferedReader(new FileReader("file1.txt"));
        BufferedReader br2 = new BufferedReader(new FileReader("file2.txt"));

        String line1 = br1.readLine();
        String line2 = br2.readLine();

        // loop to copy lines of 
        // file1.txt and file2.txt 
        // to  file3.txt alternatively
        while (line1 != null || line2 !=null)
        {
            if(line1 != null)
            {
                pw.println(line1);
                line1 = br1.readLine();
            }

            if(line2 != null)
            {
                pw.println(line2);
                line2 = br2.readLine();
            }
        }

        pw.flush();

        // closing resources
        br1.close();
        br2.close();
        pw.close();

        System.out.println("Merged file1.txt and file2.txt 
alternatively into file3.txt");
    }
}
```

输出:

```
Merged file1.txt and file2.txt into file3.txt

```

**注意:**如果 cwd(当前工作目录)中存在 file3.txt，那么它将被上述程序覆盖，否则将创建新文件。

**相关文章:**

*   [C program combines the contents of the two files into the third file](https://www.geeksforgeeks.org/c-program-merge-contents-two-files-third-file/)
*   [Java program combines two files into the third file](https://www.geeksforgeeks.org/java-program-merge-two-files-third-file/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。