# Java 联网

> 原文:[https://www.geeksforgeeks.org/java-networking/](https://www.geeksforgeeks.org/java-networking/)

当笔记本电脑、台式机、服务器、智能手机和平板电脑等计算设备以及摄像机、门锁、门铃、冰箱、音频/视频系统、恒温器和各种传感器等不断扩展的物联网设备相互共享信息和数据时，这就是所谓的联网。

![Java-Networking-Tutorial](img/dffd4c517e69676db55637e840d98300.png)

简而言之，网络编程或联网这个术语与编写可以在各种计算机设备上执行的程序相关联，在这些计算机设备中，所有设备都相互连接以使用网络共享资源。在这里，我们将讨论***【Java 联网】*** 。

*   什么是 Java 网络？
*   通用网络协议
*   Java 网络术语
*   Java 网络类
*   Java 网络接口
*   套接字编程
*   Inet 地址
*   网址类别

### 什么是 Java 网络？

网络为简单的程序补充了很多能量。有了网络，单个程序就可以重新获得存储在世界任何地方的数百万台计算机中的信息。Java 是从零开始编写的领先编程语言，考虑到了网络。Java 联网是将两个或多个计算设备组合在一起以共享资源的概念。

网络上所有的 Java 程序通信都在应用层完成。J2SE 应用编程接口的**java.net**包包括执行低级通信功能的各种类和接口，使用户能够制定专注于解决问题的程序。

### 通用网络协议

如前所述，Java 编程语言的****包包括各种类和接口，它们提供了一种易于使用的方法来访问网络资源。除了类和接口之外，**java.net**包还支持两种著名的网络协议。这些是:****

1.  ******传输控制协议(TCP)–**TCP 或传输控制协议允许不同应用程序之间的安全通信。TCP 是一种面向连接的协议，这意味着一旦建立连接，数据就可以双向传输。该协议通常通过互联网协议使用。因此，TCP 也被称为 TCP/IP。TCP 有内置的方法来检查错误，并确保数据按照发送的顺序传递，使其成为传输静态图像、数据文件和网页等信息的完整协议。**** 
2.  ******用户数据报协议(UDP)–**UDP 或用户数据报协议是一种无连接协议，允许数据包在不同的应用程序之间传输。UDP 是一种更简单的互联网协议，其中不需要错误检查和恢复服务。在 UDP 中，打开连接、维护连接或终止连接都没有开销。在 UDP 中，数据被连续发送给接收方，无论他们是否收到。****

> ******注:**可以从[TCP 和 UDP 的区别中了解更多关于 TCP 和 UDP 的知识。](https://www.geeksforgeeks.org/differences-between-tcp-and-udp/)****

### ****Java 网络术语****

****在 Java 网络中，许多术语被频繁使用。这些广泛使用的 Java 网络术语如下:****

1.  ******IP 地址–**IP 地址是区分互联网或本地网络上设备的唯一地址。IP 代表“互联网协议”它包含一组规则，用于管理通过互联网或本地网络发送的数据格式。IP 地址是指可以修改的逻辑地址。它由八位字节组成。每个八位字节的范围从 0 到 255 不等。

    *   IP 地址的范围–0 . 0 . 0 . 0 到 255.255.255.255
    *   例如–192 . 168 . 0 . 1**** 
2.  ******端口号–**端口号是一种识别连接互联网或其他网络信息的特定进程到达服务器时的方法。端口号用于唯一标识不同的应用程序。端口号充当应用程序之间的通信端点。端口号与两个应用程序之间传输和通信的 IP 地址相关联。有 65，535 个端口号，但并不是每天都在使用。**** 
3.  ******协议–**网络协议是一组有组织的命令，定义了数据如何在同一网络中的不同设备之间传输。网络协议是用户可以方便地与世界各地的人进行通信的原因，因此在现代数字通信中起着至关重要的作用。例如——TCP、FTP、POP 等。**** 
4.  ******媒体访问控制地址–**媒体访问控制地址代表媒体访问控制地址。分配给网卡(网络接口控制器/卡)的标识符很奇怪。它包含一个 48 位或 64 位地址，与网络适配器相结合。MAC 地址可以用十六进制组成。简而言之，媒体访问控制地址是一个唯一的数字，用于跟踪网络中的设备。**** 
5.  ******套接字–**套接字是网络上运行的两个应用程序之间双向通信连接的一个端点。套接字机制提供了一种进程间通信(IPC)的方法，通过设置通信发生的命名接触点。套接字与端口号相关联，以便 TCP 层可以识别数据要发送到的应用程序。**** 
6.  ******面向连接和无连接的协议–**在面向连接的服务中，用户必须在开始通信之前建立连接。当连接建立时，用户可以发送消息或信息，然后他们可以释放连接。然而，在无连接协议中，数据在一条路由中从源传输到目的地，而不验证目的地是否还在，或者是否准备好接收消息。无连接协议中不需要身份验证。

    *   面向连接的协议示例——传输控制协议
    *   无连接协议示例——用户数据报协议**** 

### ****Java 网络类****

****Java 编程语言的**java.net**包包括各种类，这些类提供了一种简单易用的方法来访问网络资源。**java.net**套餐涵盖的课程如下–**** 

1.  ****[**CacheRequest–**](https://www.geeksforgeeks.org/java-net-cacherequest-class-in-java/)每当需要在 ResponseCache 中存储资源时，都会在 java 中使用 CacheRequest 类。此类的对象为 OutputStream 对象提供了将资源数据存储到缓存中的边缘。**** 
2.  ****[**CookieHandler**](https://www.geeksforgeeks.org/java-net-cookiehandler-class-in-java/)**–**CookieHandler 类在 Java 中用于实现回调机制，以保护 HTTP 协议处理程序内部的 HTTP 状态管理策略实现。HTTP 状态管理机制指定了如何发出 HTTP 请求和响应的机制。**** 
3.  ****[**CookieManager**](https://www.geeksforgeeks.org/java-net-cookiemanager-class-in-java/)**–**CookieManager 类用于提供 CookieHandler 的精确实现。这个类将 cookie 的存储与接受和拒绝 cookie 的策略分开。一个烹饪管理器包括一个烹饪存储和一个烹饪策略。**** 
4.  ****[**【数据分组】**](https://www.geeksforgeeks.org/java-net-datagrampacket-class-java/)**–**数据分组类用于为消息从一个系统到另一个系统的无连接传输提供便利。这个类提供了使用数据报套接字类为无连接传输生成数据报包的工具。**** 
5.  ****[**InetAddress**](https://www.geeksforgeeks.org/java-net-inetaddress-class-in-java/)**–**InetAddress 类用于提供获取任意主机名的 IP 地址的方法。IP 地址由 32 位或 128 位无符号数字表示。InetAddress 可以同时处理 IPv4 和 IPv6 地址。**** 
6.  ****[**【服务器套接字】**](https://www.geeksforgeeks.org/java-net-serversocket-class-in-java/)**–**服务器套接字类用于实现客户机/服务器套接字连接的服务器端的独立于系统的实现。如果服务器套接字类的构造函数无法侦听指定的端口，它将引发异常。例如，如果端口已经被使用，它将抛出一个异常。**** 
7.  ****[**【Socket】**](https://www.geeksforgeeks.org/java-net-socket-class-in-java/)**–**Socket 类用于创建 Socket 对象，帮助用户实现所有基本的 Socket 操作。用户可以执行各种网络操作，例如发送、读取数据和关闭连接。使用 **java.net.Socket** 类构建的每个 Socket 对象都与 1 台远程主机进行了精确连接；为了连接到另一个主机，用户必须创建一个新的 socket 对象。**** 
8.  ****[**DatagramSocket**](https://www.geeksforgeeks.org/java-net-datagramsocket-class-java/)**–**DatagramSocket 类是一个网络套接字，为发送和接收数据包提供了一个无连接点。从数据报套接字发送的每个数据包都是单独路由和传递的。它还可以用于发送和接收广播信息。数据报套接字是 Java 通过 UDP 而不是 TCP 提供网络通信的机制。**** 
9.  ****[**代理**](https://www.geeksforgeeks.org/java-net-proxy-class-in-java/)**–**代理是一种不变的对象，是一种工具或方法或程序或系统，用来保存其用户和计算机的数据。它的行为就像电脑和互联网用户之间的一堵墙。代理对象表示要应用于连接的代理设置。**** 
10.  ****[**URL**](https://www.geeksforgeeks.org/url-class-java-examples/)**–**Java 中的 URL 类是互联网上任何可用资源的入口点。类网址描述了统一资源定位符，它是万维网上“资源”的信号。源可以表示简单的文件或目录，也可以表示更难的对象，例如对数据库或搜索引擎的查询。**** 
11.  ****[**【URLConnection】**](https://www.geeksforgeeks.org/java-net-urlconnection-class-in-java/)**–**Java 中的 URL connection 类是一个抽象类，描述了由类似 URL 定义的资源的连接。URLConnection 类用于辅助两个不同但相互关联的目的。首先，它提供了对与服务器(尤其是 HTTP 服务器)交互的控制，而不是 URL 类。此外，使用 URLConnection，用户可以验证服务器传输的标头，并可以做出相应的反应。用户还可以使用 URLConnection 配置客户端请求中使用的标头字段。****

### ****Java 网络接口****

****Java 编程语言的**java.net**包还包括各种接口，这些接口提供了一种简单易用的方法来访问网络资源。**java.net**包中包含的接口如下:****

1.  ******CookiePolicy–****java.net**包中的 CookiePolicy 接口提供了实现各种网络应用的类。它决定哪些 cookies 应该被接受，哪些应该被拒绝。在 CookiePolicy 中，有三种预定义的策略实现，即 ACCEPT_ALL、ACCEPT_NONE 和 ACCEPT_ORIGINAL_SERVER。**** 
2.  ******CookieStore–**CookieStore 是描述 cookies 存储空间的界面。对于每个 HTTP 响应，CookieManager 将 cookie 合并到 CookieStore 中，并为每个 HTTP 请求从 CookieStore 中恢复 cookie。**** 
3.  ******文件名映射–**文件名映射接口是一个简单的接口，它实现了一个工具来概述文件名和 MIME 类型字符串。文件名称映射从数据文件中收取文件名映射(称为模拟表)。**** 
4.  ******socketopion–**socketopion 界面帮助用户控制套接字的行为。通常，在套接字中开发必要的特性是非常必要的。SocketOptions 允许用户设置各种标准选项。**** 
5.  ******SocketImplFactory–**SocketImplFactory 接口为 SocketImpl 实例定义了一个工厂。套接字类使用它来创建实现各种策略的套接字实现。**** 
6.  ******协议家族–**该接口代表一个通信协议家族。ProtocolFamily 接口包含一个名为 name()的方法，该方法返回协议家族的名称。****

### ****套接字编程****

****[**Java Socket 编程**](https://www.geeksforgeeks.org/socket-programming-in-java/) 用于在不同 JRE 上工作的应用程序之间的通信。套接字使用 TCP 实现两台计算机之间的通信工具。Java Socket 编程可以是面向连接的，也可以是无连接的。在套接字编程中，套接字和服务器套接字类是为面向连接的套接字编程而管理的。然而，数据图套接字和数据图数据包类被用于无连接套接字编程。****

****客户端应用程序在其通信端生成一个套接字，并努力将该套接字与服务器相结合。当连接建立时，服务器在其通信端生成一个套接字类的对象。客户端和服务器现在可以通过读写套接字进行通信。****

******java.net.Socket** 类描述了一个套接字， **java.net.ServerSocket** 类实现了一个服务器程序托管客户端并与之建立连接的工具。

**使用套接字编程在两个计算设备之间建立 TCP 连接的步骤******

****以下是使用套接字编程在两台计算机之间建立 TCP 连接的步骤，如下所示:**** 

******步骤 1–**服务器实例化一个 ServerSocket 对象，指示将在哪个端口号进行通信。****

******步骤 2–**实例化 ServerSocket 对象后，服务器请求 ServerSocket 类的 accept()方法。该程序暂停，直到客户端连接到给定端口上的服务器。****

******步骤 3–**服务器空闲后，客户端实例化一个 Socket 类的对象，定义服务器名称和要连接的端口号。****

******步骤 4–**经过上述步骤后，Socket 类的构造函数努力将客户端连接到指定的服务器和端口号。如果通信通过验证，客户端立即拥有一个擅长与服务器交互的套接字对象。****

******步骤 5–**在服务器端，accept()方法返回对服务器上连接到客户端套接字的新套接字的引用。****

****连接稳定后，可以使用输入/输出流进行通信。套接字类的每个对象都有一个输出流和一个输入流。客户机的输出流与服务器的输入流相关联，客户机的输入流与服务器的输出流相结合。传输控制协议是一种双向通信协议。因此，信息可以在相应的时间通过两个流传输。****

### ****插座类****

******套接字类**用于创建套接字对象，帮助用户实现所有基本的套接字操作。用户可以执行各种网络操作，如发送、读取数据和关闭连接。使用 **java.net.Socket** 类创建的每个 Socket 对象都专门与一个远程主机相关联。如果用户想要连接到另一个主机，那么他必须构建一个新的套接字对象。****

******插座类方法******

****在 Socket 编程中，客户机和服务器都有一个 Socket 对象，因此 Socket 类下的所有方法都可以被客户机和服务器调用。Socket 类中有很多方法。****

<figure class="table"> ****| s No. | 

方法

 | 

描述

 |
| --- | --- | --- |
| one | **公共空连接(插座地址主机，int 超时)** | This method is used to connect a socket to a specialized host. This method is only required when the user instantiates the socket to which the parameterless constructor is applied. |
| Two | **public int getPort()** | This method is used to return the port on the remote machine where the socket is pinned. |
| three | **菲儿 InetAddress getnetaddress()** | This method is used to return the location of another computer connected to the socket. |
| four | **public int getLocalPort()** | This method is used to return the port that the socket on the local machine joined. |
| five | **菲儿 socket address getremote socket address()** | This method returns the location of the remote socket. |
| six | **菲儿 input stream getinpertstream()** | This method is used to return the input stream of the socket. The input stream is combined with the output stream of the remote socket. |
| seven | **公共输出流 getOutputStream（）** | This method is used to return the output stream of the socket. The output stream is combined with the input stream of the remote socket. |
| eight | **公共无效关闭()** | This method is used to close the Socket, which will cause the object of the socket class to be unable to connect to any server again. |**** </figure>

### ****服务器套接字类****

******服务器套接字类**用于提供客户端/服务器套接字连接的服务器端的独立于系统的实现。如果服务器套接字类的构造函数无法侦听指定的端口，它将引发异常。例如，如果端口已经被使用，它将抛出一个异常。****

******服务器套接字类的方法:******

****ServerSocket 类中有很多方法对用户非常有用。这些方法是:**** 

<figure class="table"> ****| s No. | 

方法

 | 

描述

 |
| --- | --- | --- |
| one | **公共获取本地端口（）** | This method is used to return the port that the server socket is monitoring. This method is beneficial if the user passes 0 as the port number in the constructor and asks the server to find a port for him. |
| Two | **公共 void setSoTimeout(int time out)** | This method is used to set the timeout value for the time when the server socket of the client is suspended during the accept () method. |
| three | **公共插座接受()** | This method waits for an incoming client. Considering that the timeout value has been set by using the setSoTimeout () method, this method will be blocked until the client combines with the server on the specified port or the socket times out. Otherwise, this method will be blocked indefinitely. |
| four | **公共空绑定(套接字地址主机，int backlog)** | This method is used to bind the socket to the specific server and port in the SocketAddress object. This method should be used if the user has already instantiated the server socket using the parameterless constructor. |**** </figure>

#### ****Java 套接字编程示例:****

****下面的例子说明了一个非常基本的单向客户机和服务器设置，其中客户机连接，向服务器发送消息，服务器显示它们使用套接字连接。****

******客户端 Java 实现:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// A Java program for a ClientSide

import java.io.*;
import java.net.*;

public class clientSide {

    // initialize socket and input output streams
    private Socket socket = null;
    private DataInputStream input = null;
    private DataOutputStream out = null;

    // constructor to put ip address and port
    public clientSide(String address, int port)
    {

        // establish a connection
        try {

            socket = new Socket(address, port);

            System.out.println("Connected");

            // takes input from terminal
            input = new DataInputStream(System.in);

            // sends output to the socket
            out = new DataOutputStream(
                socket.getOutputStream());
        }

        catch (UnknownHostException u) {

            System.out.println(u);
        }

        catch (IOException i) {

            System.out.println(i);
        }

        // string to read message from input
        String line = "";

        // keep reading until "End" is input
        while (!line.equals("End")) {

            try {

                line = input.readLine();

                out.writeUTF(line);
            }

            catch (IOException i) {

                System.out.println(i);
            }
        }

        // close the connection
        try {

            input.close();

            out.close();

            socket.close();
        }

        catch (IOException i) {

            System.out.println(i);
        }
    }

    public static void main(String[] args)
    {

        clientSide client
            = new clientSide("127.0.0.1", 5000);
    }
}**
```

******服务器端 Java 实现:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// A Java program for a serverSide
import java.io.*;
import java.net.*;

public class serverSide {

    // initialize socket and input stream
    private Socket socket = null;
    private ServerSocket server = null;
    private DataInputStream in = null;

    // constructor with port
    public serverSide(int port)
    {

        // starts server and waits for a connection
        try {
            server = new ServerSocket(port);

            System.out.println("Server started");

            System.out.println("Waiting for a client ...");

            socket = server.accept();

            System.out.println("Client accepted");

            // takes input from the client socket
            in = new DataInputStream(
                new BufferedInputStream(
                    socket.getInputStream()));

            String line = "";

            // reads message from client until "End" is sent
            while (!line.equals("End")) {

                try {

                    line = in.readUTF();

                    System.out.println(line);
                }

                catch (IOException i) {

                    System.out.println(i);
                }
            }

            System.out.println("Closing connection");

            // close connection
            socket.close();

            in.close();
        }

        catch (IOException i) {

            System.out.println(i);
        }
    }

    public static void main(String[] args)
    {

        serverSide server = new serverSide(5000);
    }
}**
```

******在终端或命令提示符下运行******

****打开两个窗口，一个用于服务器，另一个用于客户端。****

******1。**首先运行服务器应用程序。它会显示–****

```
**Server started
Waiting for a client …**
```

******2。**然后在另一个终端上运行客户端应用程序。它将显示:****

```
**Connected** 
```

****服务器接受客户端并显示，****

```
**Client accepted**
```

******3。**然后您可以开始在客户端窗口中键入消息。这是输出的示例视频。****

****<video class="wp-video-shortcode" id="video-667791-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210824172633/Socket-Programming-Output.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210824172633/Socket-Programming-Output.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210824172633/Socket-Programming-Output.mp4)</video>****

### ****互联网地址****

****InetAddress 类用于提供获取任何主机名的 IP 地址的方法。IP 地址由 32 位或 128 位无符号数字表示。InetAddress 的一个对象用其相似的主机名来描述 IP 地址。InetAddress 可以控制 IPv4 和 IPv6 地址。****

******有两种不同类型的地址:******

*   ******单播–**是单个接口的标识符。****
*   ******多播–**它是接口集合的标识符。****

******服装类的方法******

****Java InetAddress 类表示一个 IP 地址。下面给出的是 InetAddress 类的重要方法–****

<figure class="table">

| s No. | 

方法

 | 

描述

 |
| --- | --- | --- |
| one | **inet 地址的 getByAddress(字节[** |
| Two | **静态 InetAddress getByAddress(字符串主机，字节[] addr)** | This method is used to create InetAddress based on the given host name and IP address. |
| three | **静态 InetAddress getByName(字符串主机)** | This method is used to determine the IP address of the host when the host name is given. |
| four | **静态 InetAddress InetAddress getLocalHost（）** | This method is used to return LocalHost. |
| five | **-你好 getHostName()** | This method is used to get the name of the IP address. |
| six | 字符串 getHostAddress() | This method returns the IP address as a string in the text display. |
| seven | **-你好 toString()** | This method is used to convert IP addresses into strings. |

</figure>

#### ****Inet 地址类方法示例:****

****下面是****Inet Address**类的 Java 实现，用来说明方法的用法:******

******例 1:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**import java.net.*;

public class InetAddressExample1 {

    public static void main(String[] args) throws UnknownHostException{

          // To get and print InetAddress of the Local Host
        InetAddress address = InetAddress.getLocalHost();

        System.out.println("InetAddress of the Local Host : "+address);

        // To get and print host name of the Local Host
        String hostName=address.getHostName();

        System.out.println("\nHost name of the Local Host : "+hostName);

    }

}**
```

******Output**

```
InetAddress of the Local Host : localhost/127.0.0.1

Host name of the Local Host : localhost
```**** 

******例 2:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**import java.net.*;

public class InetAddressExample2 {

    public static void main(String[] args)
        throws UnknownHostException
    {

        // To get and print InetAddress of Named Hosts
        InetAddress address1 = InetAddress.getByName(
                           "write.geeksforgeeks.org");

        System.out.println("Inet Address of named hosts : "
                                               + address1);

        // To get and print ALL InetAddress of Named Host
        InetAddress arr[] = InetAddress.getAllByName(
                            "www.geeksforgeeks.org");

        System.out.println("\nInet Address of ALL named hosts :");

        for (int i = 0; i < arr.length; i++) {

            System.out.println(arr[i]);
        }
    }
}**
```