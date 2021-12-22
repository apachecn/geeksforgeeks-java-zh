# Java 中的 Java.net.Inet6Address 类

> 原文:[https://www . geesforgeks . org/Java-net-inet 6 address-class-Java/](https://www.geeksforgeeks.org/java-net-inet6address-class-java/)

此类表示 IPv6 地址，并扩展了 InetAddress 类。此类方法提供了表示和解释 IPv6 地址的工具。
**该类方法采用以下格式输入:**

1.  **x:x:x:x:x:x:x:x:x–**这是 IPv6 地址的一般形式，其中每个 x 都可以用地址的 16 位十六进制值替换。请注意，使用这种格式时，每个“x”必须有一个值。例如

    ```java
    4B0C:0:0:0:880C:99A8:4B0:4411
    ```

2.  当地址包含多组 8 位“0”时，可以使用特殊格式来压缩地址。在这种情况下，用“:”代替 0，以缩短地址。例如，上例中的地址可以写成-

    ```java
    4B0C::880C:99A8:4B0:4411
    ```

3.  **x:x:x:x:x:x:d . d . d . d–**当必须处理混合寻址(IPv6 + IPv4)时，使用第三种格式。在这种情况下，前 12 个字节用于 IPv6 寻址，其余 4 个字节用于 IPv4 寻址。例如

    ```java
    F334::40CB:152.16.24.142
    ```

4.  **::FFFF:d . d . d–**这种类型的寻址被称为 **IPv4 映射寻址**。它用于帮助部署 IPv6 寻址。它允许使用相同的结构和套接字通过 IPv6 和 IPv4 连接的网络进行通信。前 80 位用 0 填充，用“:”表示。接下来的 32 位都是“1”，剩下的 32 位代表 IPv4 地址。例如

    ```java
    ::FFFF:152.16.24.123
    ```

**方法:**

1.  **getByAddress(String host，byte[] addr，int scope_id) :** 这用于通过将 IPv6 作用域 id 设置为给定值来创建 Inet6Address 对象。返回的对象类似于由 inetaddress . getbyaddress(String，byte[])创建的对象，带有关于作用域 id 的附加信息。

    ```java
    Syntax :public static Inet6Address getByAddress(String host,
                            byte[] addr,
                            int scope_id)
                                     throws UnknownHostException
    Parameters :
    host : host
    addr : raw ip address in network order
    scope_id : scope id of the address
    Throws :
    UnknownHostException : if IP address is of illegal length
    ```

2.  **getByAddress(String host，byte[] addr，NetworkInterface nif):** 可以使用重载方法 getByAddress()来指定与地址一起使用的网络接口。在这种情况下，对应于网络接口的作用域 id 被用作作用域 id。

    ```java
    Syntax :public static Inet6Address getByAddress(String host,
                            byte[] addr,
                            NetworkInterface nif)
                                     throws UnknownHostException
    Parameters :
    host : host
    addr : raw ip address in network order
    nif : network interface to be associated with this address
    Throws :
    UnknownHostException : if IP address is of illegal length
    ```

3.  **getScopeId() :** 返回与此地址关联的作用域 Id，如果未设置，则返回 0。

    ```java
    Syntax : public int getScopeId()
    ```

4.  **getScopedInterface() :** 返回与此地址关联的网络接口，如果未设置，则返回 null。

    ```java
    Syntax : public NetworkInterface getScopedInterface()
    ```

5.  **getAddress() :** 将此 InetAddress 对象的原始 IP 地址作为数组返回。字节在数组中出现的顺序与在 IP 地址中的顺序相同，即 getAddress[0]将包含最高顺序的字节。

    ```java
    Syntax : public byte[] getAddress()
    ```

6.  **getHostAddress() :** 以文本形式返回 IP 地址。

    ```java
    Syntax :public String getHostAddress()
    ```

7.  **is anilocaladdress():**如果该地址代表本地地址，则返回 true。

    ```java
    Syntax :public boolean isAnyLocalAddress()
    ```

8.  **islinklocaldaddress():**如果该地址是链路本地地址，则返回 true。

    ```java
    Syntax :public boolean isLinkLocalAddress()
    ```

9.  **isLoopbackAddress() :** 如果该地址是环回地址，则返回 true。

    ```java
    Syntax :public boolean isLoopbackAddress()
    ```

10.  **isMCGlobal() :** 如果此多播地址具有全局作用域，则返回 true。

    ```java
    Syntax :public boolean isMCGloabal()
    ```

11.  **IsmCellLocal():**如果此多播地址有链接范围，则返回 true。

    ```java
    Syntax :public boolean isMCLinkLocal()
    ```

12.  **如果此多播地址具有节点作用域，则 isMCNodeLocal() :** 返回 true。

    ```java
    Syntax :public boolean isMCNodeLocal()
    ```

13.  **如果此多播地址具有组织范围，则 isMCOrgLocal() :** 返回 true。

    ```java
    Syntax :public boolean isMCOrgLoacal()
    ```

14.  **如果此多播地址具有站点范围，则 ISCSITELOCAL():**返回 true。

    ```java
    Syntax :public boolean isMCSiteLocal()
    ```

15.  **isMulticastAddress() :** 如果该地址是一个 IP 多播地址，则返回 true。多播地址的前 4 位是 1110。

    ```java
    Syntax :public boolean isMulticastAddress()
    ```

16.  **如果该地址是站点本地地址，issitelocaddress():**返回 true。

    ```java
    Syntax :public boolean isSiteLocalAddress()()
    ```

17.  **hashCode() :** 返回与此地址对象关联的 hashCode。

    ```java
    Syntax : public int hashCode()
    ```

18.  **等于()**:如果该 ip 地址与指定对象的 IP 地址相同，则返回 true。Equals()方法在比较时不考虑主机名，只考虑关联的 IP 地址。

    ```java
    Syntax : public boolean equals(Object obj)
    Parameters :
    obj : object to compare with
    ```

**Java 实现:**

```java
//Java program to illustrate various
//Inet6Address class methods
import java.net.Inet6Address;
import java.net.InetAddress;
import java.net.UnknownHostException;
import java.util.Arrays;

public class inet6add 
{

    public static void main(String[] args) throws UnknownHostException 
    {

        String host = "localhost";
        byte add[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1 };

        //getByAddress() method
        Inet6Address ip1 = Inet6Address.getByAddress(host, add, 5);
        Inet6Address ip2 = Inet6Address.getByAddress(null, add, 6);

        // Following methods checks the property of the thus created object.
        // getscopeId() method
        System.out.println("Scope Id : " + ip1.getScopeId());

        // getScopedInterface() method
        System.out.println("Scoped Interface : " + ip1.getScopedInterface());

        // getAddress() method
        System.out.println("Address : " + Arrays.toString(ip1.getAddress()));

        // getHostAddress() method
        System.out.println("Host Address : " + ip1.getHostAddress());

        // isAnyLocalAddress() method
        System.out.println("isAnyLocalAddress : " + ip1.isAnyLocalAddress());

        // isLinkLocalAddress() method
        System.out.println("isLinkLocalAddress : " + ip1.isLinkLocalAddress());

        // isLoopbackAddress() method
        System.out.println("isLoopbackAddress : " + ip1.isLoopbackAddress());

        // isMCGlobal() method
        System.out.println("isMCGlobal : " + ip1.isMCGlobal());

        // isMCLinkLocal() method
        System.out.println("isMCLinkLocal : " + ip1.isMCLinkLocal());

        // isMCNodeLocal() method
        System.out.println("isMCNodeLocal : " + ip1.isMCNodeLocal());

        // isMCOrgLocal() method
        System.out.println("isMCOrgLocal : " + ip1.isMCOrgLocal());

        // isMCSiteLocal() method
        System.out.println("isMCSiteLocal : " + ip1.isMCSiteLocal());

        // isMulticastAddress() method
        System.out.println("isMulticastAddress : " + ip1.isMulticastAddress());

        // isSiteLocalAddress() method
        System.out.println("isSiteLocalAddress : " + ip1.isSiteLocalAddress());

        // hashCode() method
        System.out.println("hashCode : " + ip1.hashCode());

        // equals() method
        System.out.println("ip1==ip2 : " + ip1.equals(ip2));

    }

}
```

**输出:**

```java
Scope Id : 5
Scoped Interface : null
Address : [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1]
Host Address : 0:0:0:0:0:0:0:1%5
isAnyLocalAddress : false
isLinkLocalAddress : false
isLoopbackAddress : true
isMCGlobal : false
isMCLinkLocal : false
isMCNodeLocal : false
isMCOrgLocal : false
isMCSiteLocal : false
isMulticastAddress : false
isSiteLocalAddress : false
hashCode : 1
ip1==ip2 : true

```

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。