# 删除文本文件中重复行的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-delete-replica-line-text-file/](https://www.geeksforgeeks.org/java-program-delete-duplicate-lines-text-file/)

**先决条件:** [打印作者](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)[缓冲器](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)

给定一个文件 input.txt。我们的任务是删除其中的重复行，并将输出保存在文件中，比如 output.txt

**朴素算法:**

```
1\. Create PrintWriter object for output.txt
2\. Open BufferedReader for input.txt
3\. Run a loop for each line of input.txt
   3.1 flag = false
   3.2 Open BufferedReader for output.txt
   3.3 Run a loop for each line of output.txt
      ->  If  line of output.txt is equal to current line of input.txt 
            -> flag = true
            -> break loop

4\. Check flag, if false
     -> write current line of input.txt to output.txt
     -> Flush PrintWriter stream

5\. Close resources.

```

要成功运行以下程序，input.txt 必须存在于同一个文件夹中，或者为其提供完整路径。

```
// Java program to remove
// duplicates from input.txt and 
// save output to output.txt

import java.io.*;

public class FileOperation
{
    public static void main(String[] args) throws IOException 
    {
        // PrintWriter object for output.txt
        PrintWriter pw = new PrintWriter("output.txt");

        // BufferedReader object for input.txt
        BufferedReader br1 = new BufferedReader(new FileReader("input.txt"));

        String line1 = br1.readLine();

        // loop for each line of input.txt
        while(line1 != null)
        {
            boolean flag = false;

            // BufferedReader object for output.txt
            BufferedReader br2 = new BufferedReader(new FileReader("output.txt"));

            String line2 = br2.readLine();

            // loop for each line of output.txt
            while(line2 != null)
            {

                if(line1.equals(line2))
                {
                    flag = true;
                    break;
                }

                line2 = br2.readLine();

            }

            // if flag = false
            // write line of input.txt to output.txt
            if(!flag){
                pw.println(line1);

                // flushing is important here
                pw.flush();
            }

            line1 = br1.readLine();

        }

        // closing resources
        br1.close();
        pw.close();

        System.out.println("File operation performed successfully");
    }
}
```

输出:

```
File operation performed successfully

```

**注意:**如果在 cwd(当前工作目录)中存在 output.txt，那么它将被上述程序覆盖，否则将创建新文件。

一个**更好的解决方案**是使用 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 来存储 input.txt 的每一行，由于 Set 会忽略重复的值，所以在存储一行时，检查它是否已经存在于 HashSet 中。仅当 hashset 中不存在时，才将其写入 output.txt。

要成功运行以下程序，input.txt 必须存在于同一文件夹中，或者为它们提供完整路径。

```
// Efficient Java program to remove
// duplicates from input.txt and 
// save output to output.txt

import java.io.*;
import java.util.HashSet;

public class FileOperation
{
    public static void main(String[] args) throws IOException 
    {
        // PrintWriter object for output.txt
        PrintWriter pw = new PrintWriter("output.txt");

        // BufferedReader object for input.txt
        BufferedReader br = new BufferedReader(new FileReader("input.txt"));

        String line = br.readLine();

        // set store unique values
        HashSet<String> hs = new HashSet<String>();

        // loop for each line of input.txt
        while(line != null)
        {
            // write only if not
            // present in hashset
            if(hs.add(line))
                pw.println(line);

            line = br.readLine();

        }

        pw.flush();

        // closing resources
        br.close();
        pw.close();

        System.out.println("File operation performed successfully");
    }
}
```

输出:

```
File operation performed successfully

```

**注意:**如果在 cwd(当前工作目录)中存在 output.txt，那么它将被上述程序覆盖，否则将创建新文件。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。