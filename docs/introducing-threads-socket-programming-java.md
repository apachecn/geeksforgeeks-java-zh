# 在 Java 套接字编程中引入线程

> 原文:[https://www . geesforgeks . org/introduction-threads-socket-programming-Java/](https://www.geeksforgeeks.org/introducing-threads-socket-programming-java/)

**先决条件:**[Java 中的 Socket 编程](https://www.geeksforgeeks.org/socket-programming-in-java/)

本文假设您已经掌握了 java 套接字编程的基本知识以及通信中使用的客户机-服务器模型的基本细节。

**网络编程为什么要使用线程？**

原因很简单，我们不希望在特定时间只有一个客户端连接到服务器，而是希望同时有多个客户端。我们希望我们的架构能够同时支持多个客户端。出于这个原因，我们必须在服务器端使用线程，以便每当客户端请求到来时，可以分配一个单独的线程来处理每个请求。

让我们举个例子，假设一个日期时间服务器位于一个地方，比如 x。作为一个通用服务器，它不为任何特定的客户端服务，而是为一整套通用客户端服务。还假设在特定时间，两个请求到达服务器。使用我们的基本服务器-客户端程序，即使是一秒钟的请求也能够连接到服务器，而另一个请求将被拒绝，因为没有提供同时处理多个请求的机制。为了克服这个问题，我们在网络编程中使用线程。
下面的文章将重点介绍**创建一个简单的日期时间服务器，用于同时处理多个客户端请求**。

**快速概览**

正常情况下，我们会创建两个 java 文件，**Server.java**和**Client.java**。服务器文件包含两个类，即**服务器**(用于创建服务器的公共类)和**客户端处理程序**(用于使用多线程处理任何客户端)。客户端文件只包含一个公共类**客户端**(用于创建客户端)。下面是这三个类如何相互作用的流程图。

![Date-time-server-1](img/96cf4263950d3ab6ae0d3cdeffba5097.png)

**服务器端编程(Server.java)**

*   **服务器类:**服务器端涉及的步骤与文章【Java 中的 T2】Socket Programming 类似，只是在获取了流和端口号之后，稍微做了一些改动，创建了线程对象。
    1.  **建立连接:**服务器套接字对象被初始化，在 while 循环中，套接字对象持续接受传入的连接。
    2.  **获取流:**输入流对象和输出流对象是从当前请求的套接字对象中提取的。
    3.  **创建处理程序对象:**获取流和端口号后，使用这些参数创建一个新的 clientHandler 对象(上面的类)。
    4.  **调用 [start()](https://www.geeksforgeeks.org/start-function-multithreading-java/) 方法:**在这个新创建的线程对象上调用 start()方法。
*   **ClientHandler 类:**由于我们将为每个请求使用单独的线程，让我们理解 ClientHandler 类扩展线程的工作和实现。每当请求到来时，这个类的一个对象将被实例化。
    1.  首先，这个类扩展了[线程](https://www.geeksforgeeks.org/java-lang-thread-class-java/)，使得它的对象具有线程的所有属性。
    2.  其次，这个类的构造函数取三个参数，可以唯一标识任何传入的请求，即一个 **Socket** ，一个 **[DataInputStream](https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-1/)** 读取，一个 **[DataOutputStream](https://www.geeksforgeeks.org/dataoutputstream-in-java/)** 写入。每当我们收到客户端的任何请求，服务器都会提取其端口号、DataInputStream 对象和 DataOutputStream 对象，并创建一个这个类的新线程对象，并在其上调用 [start()](https://www.geeksforgeeks.org/start-function-multithreading-java/) 方法。
        *注意:每个请求总会有一个套接字、输入流和输出流的三元组。这确保了这个类的每个对象都在一个特定的流上写，而不是在多个流上写。*
    3.  在该类的 **run()** 方法内部，它执行三个操作:请求用户指定是否需要时间或日期，从输入流对象中读取答案，并相应地将输出写入输出流对象。

```java
// Java implementation of  Server side
// It contains two classes : Server and ClientHandler
// Save file as Server.java

import java.io.*;
import java.text.*;
import java.util.*;
import java.net.*;

// Server class
public class Server 
{
    public static void main(String[] args) throws IOException 
    {
        // server is listening on port 5056
        ServerSocket ss = new ServerSocket(5056);

        // running infinite loop for getting
        // client request
        while (true) 
        {
            Socket s = null;

            try 
            {
                // socket object to receive incoming client requests
                s = ss.accept();

                System.out.println("A new client is connected : " + s);

                // obtaining input and out streams
                DataInputStream dis = new DataInputStream(s.getInputStream());
                DataOutputStream dos = new DataOutputStream(s.getOutputStream());

                System.out.println("Assigning new thread for this client");

                // create a new thread object
                Thread t = new ClientHandler(s, dis, dos);

                // Invoking the start() method
                t.start();

            }
            catch (Exception e){
                s.close();
                e.printStackTrace();
            }
        }
    }
}

// ClientHandler class
class ClientHandler extends Thread 
{
    DateFormat fordate = new SimpleDateFormat("yyyy/MM/dd");
    DateFormat fortime = new SimpleDateFormat("hh:mm:ss");
    final DataInputStream dis;
    final DataOutputStream dos;
    final Socket s;

    // Constructor
    public ClientHandler(Socket s, DataInputStream dis, DataOutputStream dos) 
    {
        this.s = s;
        this.dis = dis;
        this.dos = dos;
    }

    @Override
    public void run() 
    {
        String received;
        String toreturn;
        while (true) 
        {
            try {

                // Ask user what he wants
                dos.writeUTF("What do you want?[Date | Time]..\n"+
                            "Type Exit to terminate connection.");

                // receive the answer from client
                received = dis.readUTF();

                if(received.equals("Exit"))
                { 
                    System.out.println("Client " + this.s + " sends exit...");
                    System.out.println("Closing this connection.");
                    this.s.close();
                    System.out.println("Connection closed");
                    break;
                }

                // creating Date object
                Date date = new Date();

                // write on output stream based on the
                // answer from the client
                switch (received) {

                    case "Date" :
                        toreturn = fordate.format(date);
                        dos.writeUTF(toreturn);
                        break;

                    case "Time" :
                        toreturn = fortime.format(date);
                        dos.writeUTF(toreturn);
                        break;

                    default:
                        dos.writeUTF("Invalid input");
                        break;
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

        try
        {
            // closing resources
            this.dis.close();
            this.dos.close();

        }catch(IOException e){
            e.printStackTrace();
        }
    }
}
```

**输出**

```java
A new client is connected : Socket[addr=/127.0.0.1,port=60536,localport=5056]
Assigning new thread for this client
Client Socket[addr=/127.0.0.1,port=60536,localport=5056] sends exit...
Closing this connection.
Connection closed

```

**客户端编程(Client.java)**

客户端编程类似于一般的套接字编程程序，步骤如下-

1.  **建立插座连接**
2.  **沟通**

```java
// Java implementation for a client
// Save file as Client.java

import java.io.*;
import java.net.*;
import java.util.Scanner;

// Client class
public class Client 
{
    public static void main(String[] args) throws IOException 
    {
        try
        {
            Scanner scn = new Scanner(System.in);

            // getting localhost ip
            InetAddress ip = InetAddress.getByName("localhost");

            // establish the connection with server port 5056
            Socket s = new Socket(ip, 5056);

            // obtaining input and out streams
            DataInputStream dis = new DataInputStream(s.getInputStream());
            DataOutputStream dos = new DataOutputStream(s.getOutputStream());

            // the following loop performs the exchange of
            // information between client and client handler
            while (true) 
            {
                System.out.println(dis.readUTF());
                String tosend = scn.nextLine();
                dos.writeUTF(tosend);

                // If client sends exit,close this connection 
                // and then break from the while loop
                if(tosend.equals("Exit"))
                {
                    System.out.println("Closing this connection : " + s);
                    s.close();
                    System.out.println("Connection closed");
                    break;
                }

                // printing date or time as requested by client
                String received = dis.readUTF();
                System.out.println(received);
            }

            // closing resources
            scn.close();
            dis.close();
            dos.close();
        }catch(Exception e){
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
What do you want?[Date | Time]..
Type Exit to terminate connection.
Date
2017/06/16
What do you want?[Date | Time]..
Type Exit to terminate connection.
Time
05:35:28
What do you want?[Date | Time]..
Type Exit to terminate connection.
Geeks
Invalid input
What do you want?[Date | Time]..
Type Exit to terminate connection.
Exit
Closing this connection : Socket[addr=localhost/127.0.0.1,port=5056,localport=60536]
Connection closed

```

**这些程序是如何协同工作的？**

1.  当一个客户机(比如 client1)发送一个连接到服务器的请求时，服务器会分配一个新的线程来处理这个请求。新分配的线程被授予访问流的权限，以便与客户端通信。
2.  分配新线程后，服务器通过其 while 循环再次进入接受状态。
3.  当第二个请求到来时，第一个请求仍在处理中，服务器接受这个请求，并再次分配一个新的线程来处理它。这样，即使某些请求正在处理中，也可以处理多个请求。

**如何在你的系统上测试上述程序？**

将两个程序保存在同一个包中或任何地方。然后先跑 Server.java，再跑 Client.java。您可以将客户端程序复制到两个三个独立的文件中并单独运行它们，或者如果您有一个类似 eclipse 的 IDE，则可以从同一个程序中运行多个实例。上面显示的输出来自单个客户端程序，如果使用多个客户端，将获得类似的结果。

**下一个:**多线程聊天应用:[服务器端编程](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-1/)[客户端编程](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-2/)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。