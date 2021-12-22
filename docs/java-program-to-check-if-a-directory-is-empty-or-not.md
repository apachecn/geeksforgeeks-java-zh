# 检查目录是否为空的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查目录是否为空/](https://www.geeksforgeeks.org/java-program-to-check-if-a-directory-is-empty-or-not/)

类 **java.io.File** 中定义的 **list()方法**，用于获取其路径名定义的指定目录中存在的文件和文件夹(目录)的列表。文件列表存储在字符串数组中。如果数组的长度大于 0，则指定的目录不为空，否则为空。

**方法 1:使用 list()方法**

*   Suppose there is a directory in the path /home/user/folder with three text files.
*   Use the list () method to create an array and store the file name.
*   Calculate the length of the string array.
*   Print results

上述方法见下面的程序。

## 爪哇

T5

```java
// Java Program to check if 
// a directory is empty or not

import java.io.File;

class GFG {

    public static void main(String[] args)
    {
        // mention the directory path
        File directory = new File("/home/mayur");

        if (directory.isDirectory()) {

            // creating a String Array
            // store name of files
            String arr[] = directory.list();

            // check if length is greater than 0 or not
            if (arr.length > 0) {
                System.out.println("The directory "
                                   + directory.getPath()
                                   + " is not Empty!");
            }
            else {
                System.out.println("The directory "
                                   + directory.getPath()
                                   + " is Empty!");
            }
        }
    }
}
```