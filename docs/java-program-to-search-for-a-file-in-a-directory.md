# 在目录中搜索文件的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-search-for-a-file-in-a-directory/](https://www.geeksforgeeks.org/java-program-to-search-for-a-file-in-a-directory/)

在 Java 中搜索文件可以使用文件类和文件名过滤器界面来执行。FilenameFilter 接口用于从文件列表中过滤文件。这个接口有一个方法**布尔 accept(File dir，String name)** ，实现这个方法是为了从 java.io.File.list()方法返回的列表中找到想要的文件。当我们想要在一个文件夹中找到具有特定扩展名的文件时，这种方法非常有用。

**第一种方法**

1.  Create a class MyFilenameFilter that implements the FilenameFilter interface, and override the accept () method of the Filename Filter interface.
2.  The accept () method has two parameters, the first is the directory name and the second is the file name.
3.  The accept () method returns true if the file name begins with the specified initials, otherwise it returns false.
4.  Class FindFile contains the main methods to accept user input, such as directories to be searched and initials of files to be searched.
5.  The directory object of the File class is initiated by the director name, and the filter object of the MyFilenameFilter class is initiated by the initials provided by the user.
6.  Call the list () method on the dir object to return an array of files that meet the conditions.
7.  The array is iterated and the name of the required file is printed to the output screen.

**代码实现**

## Java

```java
// Java Program to Search for a File in a Directory
import java.io.*;

// MyFilenameFilter class implements FilenameFilter
// interface
class MyFilenameFilter implements FilenameFilter {

    String initials;

    // constructor to initialize object
    public MyFilenameFilter(String initials)
    {
        this.initials = initials;
    }

    // overriding the accept method of FilenameFilter
    // interface
    public boolean accept(File dir, String name)
    {
        return name.startsWith(initials);
    }
}

public class Main {

    public static void main(String[] args)
    {
        // Create an object of the File class
        // Replace the file path with path of the directory
        File directory = new File("/home/user/");

        // Create an object of Class MyFilenameFilter
        // Constructor with name of file which is being
        // searched
        MyFilenameFilter filter
            = new MyFilenameFilter("file.cpp");

        // store all names with same name 
        // with/without extension
        String[] flist = directory.list(filter);

        // Empty array
        if (flist == null) {
            System.out.println(
                "Empty directory or directory does not exists.");
        }
        else {

            // Print all files with same name in directory
            // as provided in object of MyFilenameFilter
            // class
            for (int i = 0; i < flist.length; i++) {
                System.out.println(flist[i]+" found");
            }
        }
    }
}
```