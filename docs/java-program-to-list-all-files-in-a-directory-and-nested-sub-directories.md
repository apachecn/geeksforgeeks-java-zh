# 列出目录和嵌套子目录中所有文件的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-list-all-files-in-a-directory-and-nested-子目录/](https://www.geeksforgeeks.org/java-program-to-list-all-files-in-a-directory-and-nested-sub-directories/)

**先决条件:** [档案类](https://www.geeksforgeeks.org/file-class-in-java/)

给定一个主目录/文件夹，列出其中的所有文件，如果这个目录有其他嵌套的子目录，列出其中的文件。在上面的问题中很容易观察到一个简单的递归模式。

**算法:**

1.  Create a File object for the home directory.
2.  Gets the file array of the home directory.
3.  If the array [i] is a file:
    *   Print out the file name.
4.  If the array [i] is a directory:
    *   Print out the directory name.
    *   Gets the file array of the current subdirectory.
    *   Repeat steps 3 and 4 with the current subdirectory.
5.  Repeat steps 3 and 4 with the next array [I].

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print all files
// in a folder(and sub-folders)

import java.io.File;

public class GFG {
    static void RecursivePrint(File[] arr, int index, int level)
    {
        // terminate condition
        if (index == arr.length)
            return;

        // tabs for internal levels
        for (int i = 0; i < level; i++)
            System.out.print("\t");

        // for files
        if (arr[index].isFile())
            System.out.println(arr[index].getName());

        // for sub-directories
        else if (arr[index].isDirectory()) {
            System.out.println("[" + arr[index].getName()
                               + "]");

            // recursion for sub-directories
            RecursivePrint(arr[index].listFiles(), 0,
                           level + 1);
        }

        // recursion for main directory
        RecursivePrint(arr, ++index, level);
    }

    // Driver Method
    public static void main(String[] args)
    {
        // Provide full path for directory(change
        // accordingly)
        String maindirpath
            = "C:\\Users\\Gaurav Miglani\\Desktop\\Test";

        // File object
        File maindir = new File(maindirpath);

        if (maindir.exists() && maindir.isDirectory()) {

              // array for files and sub-directories
            // of directory pointed by maindir
            File arr[] = maindir.listFiles();

            System.out.println(
                "**********************************************");
            System.out.println(
                "Files from main directory : " + maindir);
            System.out.println(
                "**********************************************");

            // Calling recursive method
            RecursivePrint(arr, 0, 0);
        }
    }
}
```

**输出:**

```java
**********************************************
Files from main directory : C:\Users\Gaurav Miglani\Desktop\Test
**********************************************
Cormen.pdf
Extra-Items.pdf
XYZ.pdf
[Docs]
    A.docx
    B.doc
    C.docx
ABC.pdf
JKL.pdf
[sheets]
    XXX.csv
    YYY.csv
results.pdf
[Resumes]
    [Before2016]
        Resume2015.doc
        Resume2016.doc
        [Before2014]
            Resume2014.doc
    Resume2017.doc
    Resume2017.pdf
        QA.doc
Testing.pdf
```

**例 2:** 下面是另一个递归程序。这里我们只对嵌套子目录使用递归。对于主目录文件，我们使用 [foreach 循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)。

## Java

```java
// Recursive Java program to print all files
// in a folder(and sub-folders)

import java.io.File;

public class GFG {
    static void RecursivePrint(File[] arr, int level)
    {
        // for-each loop for main directory files
        for (File f : arr) {
            // tabs for internal levels
            for (int i = 0; i < level; i++)
                System.out.print("\t");

            if (f.isFile())
                System.out.println(f.getName());

            else if (f.isDirectory()) {
                System.out.println("[" + f.getName() + "]");

                // recursion for sub-directories
                RecursivePrint(f.listFiles(), level + 1);
            }
        }
    }

    // Driver Method
    public static void main(String[] args)
    {
        // Provide full path for directory(change
        // accordingly)
        String maindirpath
            = "C:\\Users\\Gaurav Miglani\\Desktop\\Test";

        // File object
        File maindir = new File(maindirpath);

        if (maindir.exists() && maindir.isDirectory()) {
            // array for files and sub-directories
            // of directory pointed by maindir
            File arr[] = maindir.listFiles();

            System.out.println(
                "**********************************************");
            System.out.println(
                "Files from main directory : " + maindir);
            System.out.println(
                "**********************************************");

            // Calling recursive method
            RecursivePrint(arr, 0);
        }
    }
}
```

**输出:**

```java
**********************************************
Files from main directory : C:\Users\Gaurav Miglani\Desktop\Test
**********************************************
Cormen.pdf
Extra-Items.pdf
XYZ.pdf
[Docs]
    A.docx
    B.doc
    C.docx
ABC.pdf
JKL.pdf
[sheets]
    XXX.csv
    YYY.csv
results.pdf
[Resumes]
    [Before2016]
        Resume2015.doc
        Resume2016.doc
        [Before2014]
            Resume2014.doc
    Resume2017.doc
    Resume2017.pdf
        QA.doc
Testing.pdf
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢极客博客并想投稿，你可以用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章，或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。