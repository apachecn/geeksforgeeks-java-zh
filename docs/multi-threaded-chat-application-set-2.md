# Java 多线程聊天应用|第二集(客户端编程)

> 原文:[https://www . geesforgeks . org/多线程-聊天-应用-设置-2/](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-2/)

先决条件:[在 socket 编程中引入线程](https://www.geeksforgeeks.org/introducing-threads-socket-programming-java/)，[多线程聊天应用|设置 1](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-1/)

本文给出了多线程聊天应用程序客户端程序的实现。到目前为止，套接字编程中的所有示例都假设客户端首先发送一些信息，然后服务器或其他客户端响应这些信息。
在现实世界中，情况可能并非如此。不需要向某人发送消息就能接收到消息。每当消息被传递给客户端时，客户端应该能够很容易地接收到消息，即发送和接收必须作为单独的活动而不是顺序的来实现。
有一个非常简单的解决方案，使用线程来实现这个功能。在客户端实现中，我们将创建两个线程:

1.  **发送消息:**此线程将用于向其他客户端发送消息。工作非常简单，它需要输入要发送的消息和要送达的收件人。请注意，此实现假设消息的格式为**消息#收件人**，其中收件人是收件人的姓名。然后，它将消息写入连接到该客户端处理程序的输出流。处理程序分解消息和接收者部分，并将其传递给特定的接收者。让我们看看如何实现这个线程。

    ```java
    Thread sendMessage = new Thread(new Runnable() {
                @Override
                public void run() {
                    while (true) {

                        // read the message to deliver.
                        String msg = sc.nextLine();
                        try {

                            // write on the output stream
                            dos.writeUTF(msg);
                        } catch (IOException e) {
                            e.printStackTrace();
                        }
                    }
                }
            });
    ```

2.  **读取消息:**创建接收消息的线程也采用了类似的方法。当任何客户端试图在该客户端的输入流上进行写入时，我们使用 readUTF()方法来读取该消息。下面这个线程是如何实现的片段如下所示-

    ```java
    Thread readMessage = new Thread(new Runnable() {

                @Override
                public void run() {

                    while (true) {
                        try {

                            // read the message sent to this client
                            String msg = dis.readUTF();
                            System.out.println(msg);
                        } catch (IOException e) {

                            e.printStackTrace();
                        }
                    }
                }
            });
    ```

客户端编程的其余步骤类似于前面的示例。简要解释如下–

1.  **建立插座连接**
2.  **通信**
    通信是在 readMessage 和 sendMessage 线程的帮助下进行的。用于读取和写入的独立线程确保了消息的同时发送和接收。

```java
// Java implementation for multithreaded chat client
// Save file as Client.java

import java.io.*;
import java.net.*;
import java.util.Scanner;

public class Client 
{
    final static int ServerPort = 1234;

    public static void main(String args[]) throws UnknownHostException, IOException 
    {
        Scanner scn = new Scanner(System.in);

        // getting localhost ip
        InetAddress ip = InetAddress.getByName("localhost");

        // establish the connection
        Socket s = new Socket(ip, ServerPort);

        // obtaining input and out streams
        DataInputStream dis = new DataInputStream(s.getInputStream());
        DataOutputStream dos = new DataOutputStream(s.getOutputStream());

        // sendMessage thread
        Thread sendMessage = new Thread(new Runnable() 
        {
            @Override
            public void run() {
                while (true) {

                    // read the message to deliver.
                    String msg = scn.nextLine();

                    try {
                        // write on the output stream
                        dos.writeUTF(msg);
                    } catch (IOException e) {
                        e.printStackTrace();
                    }
                }
            }
        });

        // readMessage thread
        Thread readMessage = new Thread(new Runnable() 
        {
            @Override
            public void run() {

                while (true) {
                    try {
                        // read the message sent to this client
                        String msg = dis.readUTF();
                        System.out.println(msg);
                    } catch (IOException e) {

                        e.printStackTrace();
                    }
                }
            }
        });

        sendMessage.start();
        readMessage.start();

    }
}
```

**输出:**
**来自客户端 0 :**

```java
hello#client 1
client 1 : heya
how are you#client 1
client 1 : fine..how about you
logout

```

**来自客户端 1 :**

```java
client 0 : hello
heya#client 0
client 0 : how are you
fine..how about you#client 0
logout

```

**要点:**

*   要从任何客户端发送消息，请键入消息，后跟“#”，然后是接收客户端的名称。请注意，此实现给出的名称为“客户端 0”、“客户端 1”…。客户端 n”等小心翼翼的名称必须附加在末尾。之后按回车键。
*   消息发送后，该客户端的处理程序将接收消息，并将其传递给指定的客户端。
*   如果任何客户端向该客户端发送消息，readMessage 线程将自动在控制台上打印该消息。
*   一旦客户端完成了聊天，他可以发送一个没有任何收件人姓名的“注销”消息，这样服务器就会知道这个客户端已经注销了系统。建议在为客户端关闭终端之前发送注销消息，以避免任何错误。

**如何运行上述程序？**

与前面的示例类似，首先运行服务器，然后运行客户端的多个实例。从每个客户端，尝试发送消息给对方。请确保您只向有效的客户端发送消息，即向活动列表中可用的客户端发送消息。

**建议的改进措施**

这只是解释如何使用线程和套接字编程来创建强大的程序的一部分。对于上述实现，有一些建议供感兴趣的读者参考-

*   为发送和接收消息的客户端创建图形用户界面。像 Netbeans 这样的工具可以用来快速设计界面
*   目前，这些名称被硬编码为客户端 0、客户端 1。这可以改进为使用用户给定的昵称。
*   这个实现可以被进一步增强，以向客户端提供当前活动用户的列表，以便他可以知道他的所有朋友都在线。一个简单的方法可以实现这个目的，当被调用时，打印活动列表中的名字。

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。