# 用 Java 创建异步多线程聊天应用程序

> 原文:[https://www . geesforgeks . org/creating-异步多线程-聊天-java 应用程序/](https://www.geeksforgeeks.org/creating-an-asynchronous-multithreaded-chat-application-in-java/)

先决条件:[Java 中的数据报](https://www.geeksforgeeks.org/datagrams-in-java/)

在本文中，我们将学习如何在 java 中使用 **[【数据报】](https://www.geeksforgeeks.org/datagrams-in-java/)** 在 Java 中创建异步消息应用程序。 **[异步](https://www.geeksforgeeks.org/difference-between-synchronous-and-asynchronous-sequential-circuits/)在此上下文中的意思是，服务器和客户端都可以独立地向对方发送文本***，而无需等待对方的任何响应。*** 我们将利用[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)的概念，借助*datagrammpackets*实现进程间发送和接收短信。数据报是应用程序之间传递的信息包。一旦数据报被释放到它的预定目标，它是独立的，并且不能保证它会到达，甚至不能保证某个应用程序会在那里接收它。Java 在 **[UDP(用户数据报协议)](https://www.geeksforgeeks.org/computer-network-user-datagram-protocol-udp/)** 协议之上实现数据报。**

****以下是上述办法的实施情况。****

## **unsyncchatserver . java**

```java
import java.net.*;
import java.io.*;
import java.util.*;

public class UnSyncChatServer {

    public static void main(String args[])
        throws IOException, InterruptedException
    {

        // Create DatagramSocket and get ip
        DatagramSocket ss = new DatagramSocket(1234);
        InetAddress ip = InetAddress.getLocalHost();

        System.out.println("Running UnSyncChatServer.java");

        System.out.println("Server is Up....");

        // Create a sender thread
        // with a nested runnable class definition
        Thread ssend;
        ssend = new Thread(new Runnable() {
            @Override
            public void run()
            {
                try {
                    Scanner sc = new Scanner(System.in);
                    while (true) {
                        synchronized (this)
                        {
                            byte[] sd = new byte[1000];

                            // scan new message to send
                            sd = sc.nextLine().getBytes();
                            DatagramPacket sp
                                = new DatagramPacket(
                                    sd,
                                    sd.length,
                                    ip,
                                    5334);

                            // send the new packet
                            ss.send(sp);

                            String msg = new String(sd);
                            System.out.println("Server says: "
                                               + msg);

                            // exit condition
                            if ((msg).equals("bye")) {
                                System.out.println("Server"
                                                   + " exiting... ");
                                break;
                            }
                            System.out.println("Waiting for"
                                               + " client response... ");
                        }
                    }
                }
                catch (Exception e) {
                    System.out.println("Exception occured");
                }
            }
        });

        Thread sreceive;
        sreceive = new Thread(new Runnable() {
            @Override
            public void run()
            {
                try {
                    while (true) {
                        synchronized (this)
                        {

                            byte[] rd = new byte[1000];

                            // Receive new message
                            DatagramPacket sp1
                                = new DatagramPacket(
                                    rd,
                                    rd.length);
                            ss.receive(sp1);

                            // Convert byte data to string
                            String msg
                                = (new String(rd)).trim();
                            System.out.println("Client ("
                                               + sp1.getPort()
                                               + "):"
                                               + " "
                                               + msg);

                            // Exit condition
                            if (msg.equals("bye")) {
                                System.out.println("Client"
                                                   + " connection closed.");
                                break;
                            }
                        }
                    }
                }
                catch (Exception e) {
                    System.out.println("Exception occured");
                }
            }
        });

        ssend.start();
        sreceive.start();

        ssend.join();
        sreceive.join();
    }
}
```

## **unsyncchatclient . java**

```java
import java.io.*;
import java.net.*;
import java.util.Scanner;

public class UnSyncChatClient {

    public static void main(String args[])
        throws IOException, InterruptedException
    {

        // create DatagramSocket and get ip
        DatagramSocket cs
            = new DatagramSocket(5334);
        InetAddress ip
            = InetAddress.getLocalHost();

        System.out.println("Running UnSyncChatClient.java");

        System.out.println("Client is Up....");

        // create a sender thread with a nested
        // runnable class definition
        Thread csend;
        csend = new Thread(new Runnable() {
            @Override
            public void run()
            {
                try {
                    Scanner sc = new Scanner(System.in);
                    while (true) {
                        synchronized (this)
                        {
                            byte[] sd = new byte[1000];

                            // scan new message to send
                            sd = sc.nextLine().getBytes();

                            // create datagram packet
                            // for new message
                            DatagramPacket sp
                                = new DatagramPacket(
                                    sd,
                                    sd.length,
                                    ip,
                                    1234);

                            // send the new packet
                            cs.send(sp);

                            String msg = new String(sd);
                            System.out.println("Client says: "
                                               + msg);
                            // exit condition
                            if (msg.equals("bye")) {
                                System.out.println("client "
                                                   + "exiting... ");
                                break;
                            }
                            System.out.println("Waiting for "
                                               + "server response...");
                        }
                    }
                }
                catch (IOException e) {
                    System.out.println("Exception occured");
                }
            }
        });

        // create a receiver thread with a nested
        // runnable class definition
        Thread creceive;
        creceive = new Thread(new Runnable() {
            @Override
            public void run()
            {
                try {

                    while (true) {
                        synchronized (this)
                        {

                            byte[] rd = new byte[1000];

                            // receive new message
                            DatagramPacket sp1
                                = new DatagramPacket(
                                    rd,
                                    rd.length);
                            cs.receive(sp1);

                            // convert byte data to string
                            String msg = (new String(rd)).trim();
                            System.out.println("Server: " + msg);

                            // exit condition
                            if (msg.equals("bye")) {
                                System.out.println("Server"
                                                   + " Stopped....");
                                break;
                            }
                        }
                    }
                }
                catch (IOException e) {
                    System.out.println("Exception occured");
                }
            }
        });

        csend.start();
        creceive.start();

        csend.join();
        creceive.join();
    }
}
```

****输出:窗口 1**(UnSyncChatServer.java)**

```java
Running UnSyncChatServer.java
Server is Up....
Client (5334): hey
hi
Server says: hi
Waiting for client response... 
ssup?
Server says: ssup?
Waiting for client response... 
Client (5334): good
Client (5334): u?
good as well
Server says: good as well
Waiting for client response... 
Client (5334): bye
Client connection closed.
bye
Server says: bye
Server exiting... 
```

****输出:窗口 2**(UnSyncChatClient.java)**

```java
Running UnSyncChatClient.java
Client is Up....
hey
Client says: hey
Waiting for server response...
Server: hi
Server: ssup?
good
Client says: good
Waiting for server response...
u?
Client says: u?
Waiting for server response...
Server: good as well
bye
Client says: bye
client exiting... 
Server: bye
Server Stopped... 
```

**<video class="wp-video-shortcode" id="video-289337-1" width="665" height="364" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190328221049/UnSyncChatOutput.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20190328221049/UnSyncChatOutput.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190328221049/UnSyncChatOutput.mp4)</video>**

****注:****

*   **使用脱机集成开发环境运行此程序，因为联机集成开发环境可能会超时。**
*   **首先运行程序 1，然后运行程序 2。**