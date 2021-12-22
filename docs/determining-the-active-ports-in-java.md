# 确定 Java 中的活动端口

> 原文:[https://www . geesforgeks . org/确定 java 中的活动端口/](https://www.geeksforgeeks.org/determining-the-active-ports-in-java/)

在这里，我们将了解识别用作服务器的可用和活动端口的方法。

**进场:**

1.创建套接字类的对象。

2.为 **i** 指定一个值，直到您想要查找可用端口为止。

3.将此整数和主机名传递给套接字类的对象。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check the active or available
// ports.

import java.net.*;
import java.io.*;

public class Main {
    public static void main(String[] args)
    {
        // Creating object of socket class
        Socket portCheck;

        // Defining the hostName to check for port
        // availability
        String host = "localhost";

        if (args.length > 0) {
            host = args[0];
        }
        for (int i = 0; i < 1024; i++) {
            try {
                System.out.println("Looking for " + i);
                portCheck = new Socket(host, i);
                System.out.println(
                    "There is a server running on port "
                    + i);
            }
            catch (UnknownHostException e) {
                System.out.println("Exception occured" + e);
                break;
            }
            catch (IOException e) {
            }
        }
    }
}
```

#### 输出:

![Check ports availability](img/c7babf32991207e6db080732bde36cef.png)