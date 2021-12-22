# Java 中的 Java.io.File 类

> 原文:[https://www.geeksforgeeks.org/file-class-in-java/](https://www.geeksforgeeks.org/file-class-in-java/)

文件类是 Java 对文件或目录路径名的表示。因为文件和目录名在不同的平台上有不同的格式，一个简单的字符串不足以命名它们。File 类包含几种方法，用于处理路径名、删除和重命名文件、创建新目录、列出目录内容以及确定文件和目录的几种常见属性。

*   它是文件和目录路径名的抽象表示。
*   路径名，无论是抽象的还是字符串形式，都可以是绝对的或相对的。抽象路径名的父路径可以通过调用这个类的 getParent()方法获得。
*   首先，我们应该通过传递文件名或目录名来创建文件类对象。文件系统可以对实际文件系统对象上的某些操作实施限制，例如读取、写入和执行。这些限制统称为访问权限。
*   文件类的实例是不可变的；也就是说，一旦创建，由 File 对象表示的抽象路径名将永远不会改变。

**如何创建文件对象？**
文件对象是通过传入代表文件名称的字符串、字符串或其他文件对象来创建的。例如，

```java
 File a = new File("/usr/local/bin/geeks");
```

为目录/usr/local/bin 中的 geeks 文件定义一个抽象文件名。这是一个绝对抽象的文件名。

**施工人员**

*   **文件(文件父级，字符串子级):**根据父抽象路径名和子路径名字符串创建新的文件实例。
*   **文件(字符串路径名):**通过将给定的路径名字符串转换为抽象路径名来创建新的文件实例。
*   **文件(字符串父项，字符串子项):**根据父路径名字符串和子路径名字符串创建新的文件实例。
*   **文件(URI uri) :** 通过将给定的文件:URI 转换为抽象路径名来创建新的文件实例。

**方法**

1.  **布尔 canExecute() :** 测试应用程序是否可以执行这个抽象路径名所表示的文件。
2.  **布尔 canRead()** :测试应用程序是否可以读取这个抽象路径名所表示的文件。
3.  **布尔 canWrite() :** 测试应用程序是否可以修改这个抽象路径名所表示的文件。
4.  **int compareTo(文件路径名):**按字典顺序比较两个抽象路径名。
5.  **boolean createNewFile() :** 原子性地创建一个新的空文件，由这个抽象路径名命名。
6.  **静态文件创建临时文件(字符串前缀，字符串后缀):**在默认的临时文件目录中创建一个空文件。
7.  **布尔删除():**删除由该抽象路径名表示的文件或目录。
8.  **布尔相等(对象对象):**测试该抽象路径名与给定对象的相等性。
9.  **boolean exists()** :测试该抽象路径名表示的文件或目录是否存在。
10.  **String getAbsolutePath() :** 返回该抽象路径名的绝对路径名字符串。
11.  **long getFreeSpace() :** 返回分区中未分配的字节数。
12.  **String getName() :** 返回由该抽象路径名表示的文件或目录的名称。
13.  **String getParent() :** 返回该抽象路径名的父路径名字符串。
14.  **File getParentFile() :** 返回该抽象路径名的父路径名的抽象路径名。
15.  **String getPath() :** 将此抽象路径名转换为路径名字符串。
16.  **boolean isDirectory() :** 测试该路径名表示的文件是否为目录。
17.  **boolean isFile() :** 测试该抽象路径名所表示的文件是否为普通文件。
18.  **boolean isHidden() :** 测试该抽象路径名命名的文件是否为隐藏文件。
19.  **long length() :** 返回由该抽象路径名表示的文件长度。
20.  **String[] list() :** 返回命名目录中文件和目录的字符串数组。
21.  **File[] listFiles() :** 返回表示目录中文件的抽象路径名数组。
22.  **布尔 mkdir() :** 创建由该抽象路径名命名的目录。
23.  **布尔 renameTo(文件目的地):**重命名由该抽象路径名表示的文件。
24.  **布尔 setExecutable(布尔可执行):**设置所有者执行权限的便捷方法。
25.  **boolean setReadable(布尔可读):**设置所有者读取权限的便捷方法。
26.  **布尔设置可读(布尔可读，布尔所有者只读):**设置所有者或每个人的读取权限。
27.  **布尔值 setReadOnly() :** 标记名为的文件或目录，以便只允许读取操作。
28.  **布尔设置可写(布尔可写)**:设置所有者写权限的便捷方法。
29.  **String toString() :** 返回该抽象路径名的路径名字符串。
30.  **URI 旅游():**构造一个代表这个抽象路径名的文件 URI。

**实施**

**程序 1:** 检查文件或目录是否物理存在的程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// In this program, we accepts a file or directory name from 
// command line arguments. Then the program will check if 
// that file or directory physically exist or not and 
// it displays the property of that file or directory.
import java.io.File;

// Displaying file property
class fileProperty
{
    public static void main(String[] args) {
        //accept file name or directory name through command line args
        String fname =args[0];

        //pass the filename or directory name to File object
        File f = new File(fname);

        //apply File class methods on File object
        System.out.println("File name :"+f.getName());
        System.out.println("Path: "+f.getPath());
        System.out.println("Absolute path:" +f.getAbsolutePath());
        System.out.println("Parent:"+f.getParent());
        System.out.println("Exists :"+f.exists());
        if(f.exists())
        {
            System.out.println("Is writable:"+f.canWrite());
            System.out.println("Is readable"+f.canRead());
            System.out.println("Is a directory:"+f.isDirectory());
            System.out.println("File Size in bytes "+f.length());
        }
    }
}
```

输出:

```java
File name :file.txt
Path: file.txt
Absolute path:C:\Users\akki\IdeaProjects\codewriting\src\file.txt
Parent:null
Exists :true
Is writable:true
Is readabletrue
Is a directory:false
File Size in bytes 20

```

**程序 2:** 显示目录所有内容的程序

这里我们将从键盘接受一个目录名，然后显示目录的所有内容。为此，list()方法可以用作:

```java
String arr[]=f.list();
```

在前面的语句中，list()方法会将所有目录条目复制到数组 *arr[]* 中。然后将这些数组元素 arr[i]传递给 File 对象，并测试它们，以了解它们是否代表一个文件或目录。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.BufferedReader;
import java.io.File;
import java.io.IOException;
import java.io.InputStreamReader;

//Displaying the contents of a directory
class Contents
{
    public static void main(String[] args) throws IOException {
        //enter the path and dirname from keyboard
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        System.out.println("Enter dirpath:");
        String dirpath=br.readLine();
        System.out.println("Enter the dirname");
        String dname=br.readLine();

        //create File object with dirpath and dname
        File f = new File(dirpath, dname);

        //if directory exists,then
        if(f.exists())
        {
            //get the contents into arr[]
            //now arr[i] represent either a File or Directory
            String arr[]=f.list();

            //find no. of entries in the directory
            int n=arr.length;

            //displaying the entries
            for (int i = 0; i < n ; i++) {
                System.out.println(arr[i]);
                //create File object with the entry and test
                //if it is a file or directory
                File f1=new File(arr[i]);
                if(f1.isFile())
                    System.out.println(": is a file");
                if(f1.isDirectory())
                    System.out.println(": is a directory");
            }
            System.out.println("No of entries in this directory "+n);
        }
        else
            System.out.println("Directory not found");
    }
}
```

输出:

```java
Enter dirpath:
C:\Users\akki\IdeaProjects\
Enter the dirname
codewriting
.idea
: is a directory
an1.txt
: is a file
codewriting.iml
: is a file
file.txt
: is a file
out
: is a directory
src
: is a directory
text
: is a file
No of entries in this directory 7

```

**相关帖子:**[Java 中的 FileReader 和 file writer](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。