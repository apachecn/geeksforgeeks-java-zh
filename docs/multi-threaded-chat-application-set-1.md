# Java 多线程聊天应用|集 1(服务器端编程)

> 原文:[https://www . geesforgeks . org/多线程-聊天-应用-设置-1/](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-1/)

先决条件:[在套接字编程中引入线程](https://www.geeksforgeeks.org/introducing-threads-socket-programming-java/)
在上面的文章中，创建了一个简单的日期时间服务器，它使用线程同时处理多个用户请求。它解释了网络编程中线程的基本概念。只要稍加修改，同样的概念可以用来扩展上述想法，并创建一个类似于 facebook messenger、whatsapp 等的聊天应用程序。
下面的文章将详细解释这种应用程序的实现、限制及其解决方案。
在这一集，我们将讨论服务器端编程(Server.java)，客户端编程(Client.java)在[集 2](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-2/) 中讨论。

**服务器端编程(Server.java)**

**1。服务器类:**主服务器实现简单，与上一篇文章类似。以下几点将有助于理解服务器实施:

1.  服务器运行一个无限循环来继续接受传入的请求。
2.  当请求到来时，它会分配一个新的线程来处理通信部分。
3.  服务器还将客户端名称存储到一个向量中，以跟踪连接的设备。向量存储对应于当前请求的线程对象。助手类使用这个[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)来查找消息要传递到的接收者的名字。由于这个向量包含所有的流，处理程序类可以使用它成功地将消息传递给特定的客户端。
4.  调用 [start()](https://www.geeksforgeeks.org/start-function-multithreading-java/) 方法。

**2。ClientHandler 类:**与上一篇文章类似，我们创建了一个用于处理各种请求的助手类。这一次，随着套接字和流，我们引入了一个名称变量。这将保存连接到服务器的客户端的名称。以下几点将有助于理解 ClientHandler 的实现:

*   每当处理程序接收到任何字符串时，它都会将其分解为消息和接收方部分。为此，它使用 Stringtokenizer，以“#”作为分隔符。这里假设字符串的格式始终为:

```java
message # recipient
```

*   然后，它会在连接的客户端列表中搜索收件人的姓名，并作为向量存储在服务器中。如果在客户端列表中找到收件人姓名，它将在输出流中转发邮件，并将发件人姓名作为邮件的前缀。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java implementation of  Server side
// It contains two classes : Server and ClientHandler
// Save file as Server.java

import java.io.*;
import java.util.*;
import java.net.*;

// Server class
public class Server
{

    // Vector to store active clients
    static Vector<ClientHandler> ar = new Vector<>();

    // counter for clients
    static int i = 0;

    public static void main(String[] args) throws IOException
    {
        // server is listening on port 1234
        ServerSocket ss = new ServerSocket(1234);

        Socket s;

        // running infinite loop for getting
        // client request
        while (true)
        {
            // Accept the incoming request
            s = ss.accept();

            System.out.println("New client request received : " + s);

            // obtain input and output streams
            DataInputStream dis = new DataInputStream(s.getInputStream());
            DataOutputStream dos = new DataOutputStream(s.getOutputStream());

            System.out.println("Creating a new handler for this client...");

            // Create a new handler object for handling this request.
            ClientHandler mtch = new ClientHandler(s,"client " + i, dis, dos);

            // Create a new Thread with this object.
            Thread t = new Thread(mtch);

            System.out.println("Adding this client to active client list");

            // add this client to active clients list
            ar.add(mtch);

            // start the thread.
            t.start();

            // increment i for new client.
            // i is used for naming only, and can be replaced
            // by any naming scheme
            i++;

        }
    }
}

// ClientHandler class
class ClientHandler implements Runnable
{
    Scanner scn = new Scanner(System.in);
    private String name;
    final DataInputStream dis;
    final DataOutputStream dos;
    Socket s;
    boolean isloggedin;

    // constructor
    public ClientHandler(Socket s, String name,
                            DataInputStream dis, DataOutputStream dos) {
        this.dis = dis;
        this.dos = dos;
        this.name = name;
        this.s = s;
        this.isloggedin=true;
    }

    @Override
    public void run() {

        String received;
        while (true)
        {
            try
            {
                // receive the string
                received = dis.readUTF();

                System.out.println(received);

                if(received.equals("logout")){
                    this.isloggedin=false;
                    this.s.close();
                    break;
                }

                // break the string into message and recipient part
                StringTokenizer st = new StringTokenizer(received, "#");
                String MsgToSend = st.nextToken();
                String recipient = st.nextToken();

                // search for the recipient in the connected devices list.
                // ar is the vector storing client of active users
                for (ClientHandler mc : Server.ar)
                {
                    // if the recipient is found, write on its
                    // output stream
                    if (mc.name.equals(recipient) && mc.isloggedin==true)
                    {
                        mc.dos.writeUTF(this.name+" : "+MsgToSend);
                        break;
                    }
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

输出:

```java
New client request received : Socket[addr=/127.0.0.1,port=61818,localport=1234]
Creating a new handler for this client...
Adding this client to active client list
New client request received : Socket[addr=/127.0.0.1,port=61819,localport=1234]
Creating a new handler for this client...
Adding this client to active client list
```

**限制:**
虽然服务器的上述实现设法处理了大多数场景，但是上面定义的方法存在一些缺点。

*   上述程序的一个明显观察是**如果客户端数量变大，在处理程序类中搜索时间会增加**。为了避免这种增加，可以使用两个哈希映射。一个以名称为关键字，以活动列表中的索引为值。另一个以索引为键，关联的处理程序对象为值。这样，我们可以快速查找两个 hashmaps 来匹配接收者。读者可以自行实施这种黑客攻击，以提高实施效率。
*   另一个需要注意的是，当用户断开与服务器的连接时，这个实现**不能很好地工作。因为在这个实现中不处理断开连接，所以会抛出很多错误。它可以像前面的基本 TCP 示例一样轻松实现。读者也可以在程序中实现这个特性。**

客户端程序(Client.java)与前面的文章有很大的不同，因此将在本系列的第 2 集讨论。

相关文章:[多线程聊天应用|第二集](https://www.geeksforgeeks.org/multi-threaded-chat-application-set-2/)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。