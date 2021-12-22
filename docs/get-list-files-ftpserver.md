# 如何从 FTPserver 获取文件列表？

> 原文:[https://www.geeksforgeeks.org/get-list-files-ftpserver/](https://www.geeksforgeeks.org/get-list-files-ftpserver/)

众所周知，文件传输协议是一种可靠的协议，用于在互联网上传输文件。虽然它不是一个安全的协议，所有的数据都是以明文传输的。但它是足够可靠的协议，可以通过互联网将数据从发送者发送到接收者。
**该代码讲述了使用以下过程获取您希望在 FTP 服务器上读取的所有文件的名称:**

*   在 Java 中，我们将使用**FTP 客户端**对象从 FTP 服务器读取文件。需要导入类“org . Apache . commons . net . FTP . FTPClient”来创建 Ftpclient 的实例。
*   为 FTPClient 对象调用 **connect** ()方法，以网址为参数，与建立连接。
*   使用**登录**()方法发送凭证–用户名和密码。对于正确的凭据和成功的登录，返回 true，允许用户访问服务器上的文件。
*   登录成功后，使用**列表名称**()方法获取当前工作目录下所有文件的名称。返回的列表将是一个数组，可以迭代来读取名称。
*   由于登录是成功的，所以在读取文件名后需要**注销**()次。最后调用**断开**()方法结束与连接的 FTP 服务器的关系。

```
// Java code to illustrate
// How to get a list of files from the FTPserver
import java.io.IOException;

import org.apache.commons.net.ftp.FTPClient;

public class MyFTPClass {
    public static void main(String args[])
    {

        // Create an instance of FTPClient
        FTPClient ftp = new FTPClient();
        try {
            // Establish a connection with the FTP URL
            ftp.connect("ftp.test.com");
            // Enter user details : user name and password
            boolean isSuccess = ftp.login("user", "password");

            if (isSuccess) {
                // Fetch the list of names of the files. In case of no files an
                // empty array is returned
                String[] filesFTP = ftp.listNames();
                int count = 1;
                // Iterate on the returned list to obtain name of each file
                for (String file : filesFTP) {
                    System.out.println("File " + count + " :" + file);
                    count++;
                }
            }

            ftp.logout();
        }
        catch (IOException e) {
            e.printStackTrace();
        }
        finally {
            try {
                ftp.disconnect();
            }
            catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```

本文由 **Ritika** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。