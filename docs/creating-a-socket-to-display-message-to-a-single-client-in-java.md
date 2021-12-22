# 用 Java 创建一个向单个客户端显示消息的套接字

> 原文:[https://www . geesforgeks . org/creating-socket-to-display-message-to-single-client-in-Java/](https://www.geeksforgeeks.org/creating-a-socket-to-display-message-to-a-single-client-in-java/)

本文描述了基本的客户机-服务器连接，其中客户机连接，服务器向客户机发送消息，客户机使用套接字连接显示消息。客户端程序套接字与服务器应用程序的服务器套接字建立连接，然后服务器套接字与服务器应用程序中的内部套接字连接。

**客户端程序**

客户端程序使用套接字类与服务器建立连接。Socket 对象需要服务器的地址和服务器的端口号。

## 爪哇

T5

```java
// Client program

import java.io.*;
import java.net.*;

class GFG {

    // driver function
    public static void main(String[] args)
    {
        try {

            // Create socket object by passing id address
            // and port number establish connection
            Socket socket = new Socket("localhost", 1346);
            System.out.println(
                "Connected Successfully.....");

            // Buffer reader to get all the input stream
            BufferedReader bs = new BufferedReader(
                new InputStreamReader(s.getInputStream()));
            System.out.println("Response from Server.....");

            // Print response from server
            System.out.println("Client Side : "
                               + br.readLine());
            // Close the connection
            socket.close();
        }
        catch (UnknownHostException e) {

            // Catch block for IP errors
            System.out.println("IP not found for" + e);
        }
        catch (IOException e) {

            // Catch block for data stream errors
            System.out.println("Not found data for socket"
                               + e);
        }
    }
}
```