# Java 程序将两个文件合并成第三个文件

> 原文:[https://www . geesforgeks . org/Java-program-merge-two-files-third-file/](https://www.geeksforgeeks.org/java-program-merge-two-files-third-file/)

**先决条件:** [打印作者](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)[缓冲器](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)

假设给定的两个文件是 file1.txt 和 file2.txt。我们的任务是将这两个文件合并成第三个文件，比如 file3.txt。以下是合并的步骤。

1.  Create a PrintWriter object for the file 3.txt
2.  阿云 1.txt 文件朝比奈 dreader 缓冲区
3.  Run the loop to copy every line of file 1.txt to file 3.txt.
4.  阿云 2.txt 文件朝比奈 dreader 缓冲区
5.  Run the loop to copy every line of file 2.txt to file 3.txt.
6.  Refresh the PrintWriter stream and close the resource.

要成功运行以下程序，文件 1.txt 和文件 2.txt 必须存在于同一个文件夹中，或者为它们提供完整路径。

```java
// Java program to merge two 
// files  into third file

import java.io.*;

public class FileMerge 
{
    public static void main(String[] args) throws IOException 
    {
        // PrintWriter object for file3.txt
        PrintWriter pw = new PrintWriter("file3.txt");

        // BufferedReader object for file1.txt
        BufferedReader br = new BufferedReader(new FileReader("file1.txt"));

        String line = br.readLine();

        // loop to copy each line of 
        // file1.txt to  file3.txt
        while (line != null)
        {
            pw.println(line);
            line = br.readLine();
        }

        br = new BufferedReader(new FileReader("file2.txt"));

        line = br.readLine();

        // loop to copy each line of 
        // file2.txt to  file3.txt
        while(line != null)
        {
            pw.println(line);
            line = br.readLine();
        }

        pw.flush();

        // closing resources
        br.close();
        pw.close();

        System.out.println("Merged file1.txt and file2.txt into file3.txt");
    }
}
```

输出:

```java
Merged file1.txt and file2.txt into file3.txt

```

**注意:**如果 cwd(当前工作目录)中存在 file3.txt，那么它将被上述程序覆盖，否则将创建新文件。

**相关文章:**

*   [C program combines the contents of the two files into the third file](https://www.geeksforgeeks.org/c-program-merge-contents-two-files-third-file/)
*   [Java program alternately merges two files into the third file](https://www.geeksforgeeks.org/java-program-merge-two-files-alternatively-third-file/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。