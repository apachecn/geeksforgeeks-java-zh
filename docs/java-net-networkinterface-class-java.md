# Java 中的 Java.net.NetworkInterface 类

> 原文:[https://www . geesforgeks . org/Java-net-network interface-class-Java/](https://www.geeksforgeeks.org/java-net-networkinterface-class-java/)

此类代表网络接口，包括软件和硬件、其名称、分配给它的 IP 地址列表以及所有相关信息。当我们希望在具有多个网卡的系统上使用特定接口传输数据包时，可以使用它。
**什么是网络接口？**
网络接口可以被认为是计算机连接网络的一个点。它不一定是一件硬件，但也可以在软件中实现。例如，用于测试目的的环回接口。
**方法:**

**1.getName() :** 返回该网络接口的名称。

```java
Syntax : public String getName()
```

**2 . getnetaddresses():**如果安全管理器允许，返回绑定到此网络接口的所有 Inetaddresses 的枚举。

```java
Syntax :public Enumeration getInetAddresses()
```

**3 . getinterfaceaddresses():**返回此接口上所有接口地址的列表。

```java
Syntax :public List getInterfaceAddresses()
```

**4 . getsubpixels():**返回此网络接口的所有子接口或虚拟接口的枚举。例如，eth0:2 是 eth0 的子接口。

```java
Syntax :public Enumeration getSubInterfaces()
```

**5.getParent() :** 如果是子接口，这个方法返回父接口。如果这不是子接口，此方法将返回 null。

```java
Syntax :public NetworkInterface getParent()
```

**6.getIndex() :** 返回系统分配给该网络接口的索引。索引可以用来代替长名称来指代设备上的任何接口。

```java
Syntax :public int getIndex()
```

**7.getDisplayName() :** 此方法以可读的字符串格式返回网络接口的名称。

```java
Syntax :public String getDisplayName()
```

**8.getByName() :** 查找并返回指定名称的网络接口，如果不存在则返回 null。

```java
Syntax :public static NetworkInterface getByName(String name)
                                  throws SocketException
Parameters :
name : name of network interface to search for.
Throws :
SocketException : if I/O error occurs.
```

**9.getByIndex() :** 执行与前一个函数类似的功能，使用 Index 作为搜索参数，而不是名称。

```java
Syntax :public static NetworkInterface getByIndex(int index)
                                  throws SocketException
Parameters :
index : index of network interface to search for.
Throws :
SocketException : if I/O error occurs.
```

**10.getByInetAddress() :** 此方法被广泛使用，因为它返回指定 InetAddress 绑定到的网络接口。如果一个 InetAddress 绑定到多个接口，任何一个接口都可能被返回。

```java
Syntax : public static NetworkInterface getByInetAddress(InetAddress addr)
                                         throws SocketException
Parameters : 
addr : address to search for
Throws : 
SocketException : If IO error occurs
```

**11 . getnetworkinterfaces():**返回系统上所有的网络接口。

```java
Syntax :public static Enumeration getNetworkInterfaces()
                                                          throws SocketException
Throws :
SocketException : If IO error occurs
```

**12.isUp() :** 返回一个布尔值，指示此网络接口是否已启动并正在运行。

```java
Syntax : public boolean isUp()
```

**13.isLoopback() :** 返回一个布尔值，指示该接口是否为环回接口。

```java
 Syntax : public boolean isLoopback()
```

**14.isPointToPoint() :** 返回一个布尔值，指示该接口是否为点对点接口。

```java
Syntax : public boolean isPointToPoint()
```

**15.supportsMulticast() :** 返回一个布尔值，指示此接口是否支持多播。

```java
Syntax : public boolean supportsMulticast()
```

**16.getHardwareAddress() :** 返回一个包含此接口的硬件地址(MAC)地址的字节数组。调用此方法之前，调用方必须具有适当的权限。

```java
public byte[] getHardwareAddress()
```

**17.getMTU() :** 返回该接口的最大传输单位。MTU 是基于数据包的网络中可以发送的最大数据包或帧。

```java
Syntax :public int getMTU()
```

**18.isVirtual() :** 返回一个布尔值，指示该接口是否为虚拟接口。虚拟接口与物理接口结合使用，以提供额外的值，如地址和 MTU。

```java
Syntax : public boolean isVirtual()
```

**19.equals() :** 此方法用于比较两个网络接口是否相等。如果两个网络接口绑定了相同的名称和地址，则它们是相等的。

```java
Syntax :public boolean equals(Object obj)
Parameters : 
obj : Object to compare this network interface for equality
```

**20.hashCode() :** 返回该对象的 hashCode 值。

```java
Syntax :public int hashCode()
```

**21.toString() :** 返回此对象的文本描述。

```java
Syntax :public String toString()
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//Java program to illustrate various
//networkInterface class methods.
import java.net.InetAddress;
import java.net.InterfaceAddress;
import java.net.NetworkInterface;
import java.net.SocketException;
import java.net.UnknownHostException;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.Enumeration;

public class NetworkInterfaceEx
{
    public static void main(String[] args) throws SocketException,
                                                 UnknownHostException
    {

        // getNetworkInterfaces() returns a list of all interfaces
        // present in the system.
        ArrayList<NetworkInterface> interfaces = Collections.list(
                                             NetworkInterface.getNetworkInterfaces());

        System.out.println("Information about present Network Interfaces...\n");
        for (NetworkInterface iface : interfaces)
        {
            // isUp() method used for checking whether the interface in process
            // is up and running or not.
            if (iface.isUp())
            {

                // getName() method
                System.out.println("Interface Name: " + iface.getName());

                // getDisplayName() method
                System.out.println("Interface display name: " + iface.getDisplayName());

                // gethardwareaddress() method
                System.out.println("Hardware Address: " +
                                   Arrays.toString(iface.getHardwareAddress()));

                // getParent() method
                System.out.println("Parent: " + iface.getParent());

                // getIndex() method
                System.out.println("Index: " + iface.getIndex());
                // Interface addresses of the network interface
                System.out.println("\tInterface addresses: ");

                // getInterfaceAddresses() method
                for (InterfaceAddress addr : iface.getInterfaceAddresses())
                {
                    System.out.println("\t\t" + addr.getAddress().toString());
                }
                // Interface addresses of the network interface
                System.out.println("\tInetAddresses associated with this interface: ");

                // getInetAddresses() method returns list of all
                // addresses currently bound to this interface
                Enumeration<InetAddress> en = iface.getInetAddresses();
                while (en.hasMoreElements())
                {
                    System.out.println("\t\t" + en.nextElement().toString());
                }

                // getMTU() method
                System.out.println("\tMTU: " + iface.getMTU());

                // getSubInterfaces() method
                System.out.println("\tSubinterfaces: " +
                                   Collections.list(iface.getSubInterfaces()));

                // isLoopback() method
                System.out.println("\tis loopback: " + iface.isLoopback());

                // isVirtual() method
                System.out.println("\tis virtual: " + iface.isVirtual());

                // isPointToPoint() method
                System.out.println("\tis point to point: " + iface.isPointToPoint());

                // supportsMulticast() method
                System.out.println("Supports Multicast: " + iface.supportsMulticast());

            }
        }

        // getByIndex() method returns network interface
        // with the specified index
        NetworkInterface nif = NetworkInterface.getByIndex(1);

        // toString() method is used to display textual
        // information about this network interface
        System.out.println("Network interface 1: " + nif.toString());

        // getByName() method returns network interface
        // with the specified name
        NetworkInterface nif2 = NetworkInterface.getByName("eth0");
        InetAddress ip = InetAddress.getByName("localhost");

        // getbyInetAddress() method
        NetworkInterface nif3 = NetworkInterface.getByInetAddress(ip);
        System.out.println("\nlocalhost associated with: " + nif3);

        // equals() method
        boolean eq = nif.equals(nif2);
        System.out.println("nif==nif2: " + eq);

        // hashCode() method
        System.out.println("Hashcode : " + nif.hashCode());
    }
}
```

**输出:**

```java
Information about present Network Interfaces...

Interface Name: lo
Interface display name: Software Loopback Interface 1
Hardware Address: null
Parent: null
Index: 1
    Interface addresses: 
        /127.0.0.1
        /0:0:0:0:0:0:0:1
    InetAddresses associated with this interface: 
        /127.0.0.1
        /0:0:0:0:0:0:0:1
    MTU: -1
    Subinterfaces: []
    is loopback: true
    is virtual: false
    is point to point: false
Supports Multicast: true
Interface Name: wlan5
Interface display name: Dell Wireless 1705 802.11b|g|n (2.4GHZ)
Hardware Address: [100, 90, 4, -90, 2, 15]
Parent: null
Index: 16
    Interface addresses: 
        /192.168.43.96
        /2405:205:1486:9a1b:e567:b46f:198a:fe0c
        /2405:205:1486:9a1b:8c93:9f82:6dd2:350c
        /fe80:0:0:0:e567:b46f:198a:fe0c%wlan5
    InetAddresses associated with this interface: 
        /192.168.43.96
        /2405:205:1486:9a1b:e567:b46f:198a:fe0c
        /2405:205:1486:9a1b:8c93:9f82:6dd2:350c
        /fe80:0:0:0:e567:b46f:198a:fe0c%wlan5
    MTU: 1500
    Subinterfaces: []
    is loopback: false
    is virtual: false
    is point to point: false
Supports Multicast: true
Network interface 1: name:lo (Software Loopback Interface 1)

loclhost associated with: name:lo (Software Loopback Interface 1)
nif==nif2: false
HashCode : 2544
```

如果在您的系统上运行，上述程序的输出将有所不同，因为它将显示有关您的网络接口的信息。
参考文献:
[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/NetworkInterface.html)
本文由**里沙布·马尔塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。