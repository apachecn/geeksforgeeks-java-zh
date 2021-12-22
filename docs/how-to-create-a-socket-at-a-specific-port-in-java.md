# 如何在 Java 中的特定端口创建套接字？

> 原文:[https://www . geeksforgeeks . org/如何在特定端口创建 java 套接字/](https://www.geeksforgeeks.org/how-to-create-a-socket-at-a-specific-port-in-java/)

一个[套接字](https://www.geeksforgeeks.org/socket-programming-in-java/)是网络上运行的两个程序之间双向通信链路的一个端点。套接字类用于表示客户端程序和服务器程序之间的连接。套接字编程，我们基本上是客户机-服务器编程，其中套接字用作它们之间的链接。我们需要在我们的程序中导入**[*【Java . net】*](https://www.geeksforgeeks.org/java-net-inetsocketaddress-class-java/)包，该包提供了两个类，即 Socket 类和 ServerSocket 类。套接字类实现连接的客户端，服务器套接字类实现连接的服务器端。**

****程序:****

**为了创建套接字，需要使用 socket 和 ServerSocket 类导入“[*【java.net】*](https://www.geeksforgeeks.org/java-net-inetsocketaddress-class-java/)”包，我们创建该类的对象。**

***   The server opens a ServerSocket on a well-known port and waits for input.*   At the same time, the client opens a socket with the host name of the server and this well-known port address.*   Send a request message to the server to initialize the communication session.**

****在服务器端****

```
import java.net.Socket;
ServerSocket mySsocket= new ServerSocket(portnumber);
```

> ****注意:****服务器套接字**类采用单个参数:端口号。**
> 
> **在这里，服务器套接字是通过传递一个特定的端口号来监听的。**

****在客户端****

```
import java.net.Socket;
Socket myCsocket= new Socket( address, portnumber);
```

 **> **注意:****套接字类**采用两个参数，即地址和端口号。
> 
> 这将向服务器端询问 IP 地址，然后它会在该指定端口上打开到该服务器的套接字。

**示例 1:** 服务器端

T5】Java

```
// Java program for creating socket on Server-side
// Server program depicting creation of a socket
// at a specific port

// Importing majorly Socket and ServerSocket class
// from java.net package
import java.net.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an object of ServerSocket class
            // with the custom port number - 80
            ServerSocket mySsocket = new ServerSocket(80);

            // Display commands for better readability
            System.out.println("Server started");
            System.out.println("Waiting for a client ...");

            // Here it will wait for any client which wants
            // to get connected to this server

            // Establishing a connection
            // using accept() method()
            Socket socket = mySsocket.accept();

            // Display message
            System.out.println(
                "Client accepted through the port number: "
                + mySsocket.getLocalPort());

            // getLocalPort() function returning the port
            // number which is being used
        }

        // Catch block to handle for exceptions
        catch (Exception e) {

            // Simply return/exit
            return;
        }
    }
}
```

**输出:**

```
Server started
Waiting for a client ...
Client accepted through the port number: 80
```

**示例 2:** 客户端

## Java

```
// Java program for creating socket on Client-side
// Client program depicting creation of a socket
// at a specific port

// Importing majorly Socket and ServerSocket class
// from java.net package
import java.net.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an object of Socket class where
            // port number same as server side program
            Socket myCsocket = new Socket("localhost", 80);

            // creating client with local ip address
            // port number as '80'

            // Display message for better readability
            System.out.println("Connected to Server");
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Simply return and exit the program
            return;
        }
    }
}
```

**输出:**

```
Connected to Server
```**