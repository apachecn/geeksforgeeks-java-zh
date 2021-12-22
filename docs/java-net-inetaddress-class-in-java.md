# java 中的 java.net.InetAddress 类

> 原文:[https://www . geesforgeks . org/Java-net-inetaddress-class-in-Java/](https://www.geeksforgeeks.org/java-net-inetaddress-class-in-java/)

**公共类 InetAddress** 扩展**对象**实现**可序列化:**

**java.net.InetAddress** 类提供了获取任何主机名的 IP 地址的方法。IP 地址由 32 位或 128 位无符号数字表示。互联网地址可以同时处理 IPv4 和 IPv6 地址。

地址有两种类型:

1.  **单播—** 单个接口的标识符。
2.  **多播—** 一组接口的标识符。

**服装-工厂方法:**

**InetAddress** 类用于封装数字 IP 地址和该地址的域名。**类没有可见的构造函数。InetAddress 类不能直接创建对象，因此*工厂方法*用于此目的。工厂方法是类中返回该类对象的静态方法。**

InetAddress 类–

<figure class="table">

| way | describe |
| --- | --- |
| 静态 InetAddress getLocalHost() *抛出未知主机例外* | This method returns an InetAddress instance containing the local host name and address. |
| 菲公 InetAddress getByName(字符串主机)*阿云 ununknown dhostexception* | This method returns an instance of InetAddress containing LocalHost IP and name. |
| 日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日 InetAddress[]getAllByName(字符串主机名)*阿云 unknowhostexception* | This method returns an array of InetAddress class instances containing IP addresses. |
| 日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日 InetAddress getByAddress(大和 IPAddress[] ) *阿云 ununknown dhostexception* | This method returns an InetAddress object created from the original IP address. |
| 日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日日 InetAddress getByAddress(字符串主机名，字节 IP address[])*阿云 ununknown dhostexception* | This method creates and returns an InetAddress based on the provided host name and IP address. |

</figure>

下面是 InetAddress 类的 Java 实现，演示了工厂方法的使用–

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;
import java.net.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
        throws UnknownHostException
    {
        // To get and print InetAddress of Local Host
        InetAddress address1 = InetAddress.getLocalHost();
        System.out.println("InetAddress of Local Host : "
                           + address1);

        // To get and print InetAddress of Named Host
        InetAddress address2
            = InetAddress.getByName("45.22.30.39");
        System.out.println("InetAddress of Named Host : "
                           + address2);

        // To get and print ALL InetAddresses of Named Host
        InetAddress address3[]
            = InetAddress.getAllByName("172.19.25.29");
        for (int i = 0; i < address3.length; i++) {
            System.out.println(
                "ALL InetAddresses of Named Host : "
                + address3[i]);
        }

        // To get and print InetAddresses of
        // Host with specified IP Address
        byte IPAddress[] = { 125, 0, 0, 1 };
        InetAddress address4
            = InetAddress.getByAddress(IPAddress);
        System.out.println(
            "InetAddresses of Host with specified IP Address : "
            + address4);

        // To get and print InetAddresses of Host
        // with specified IP Address and hostname
        byte[] IPAddress2
            = { 105, 22, (byte)223, (byte)186 };
        InetAddress address5 = InetAddress.getByAddress(
            "gfg.com", IPAddress2);
        System.out.println(
            "InetAddresses of Host with specified IP Address and hostname : "
            + address5);
    }
}
```

**Output**

```java
InetAddress of Local Host : localhost/127.0.0.1
InetAddress of Named Host : /45.22.30.39
ALL InetAddresses of Named Host : /172.19.25.29
InetAddresses of Host with specified IP Address : /125.0.0.1
InetAddresses of Host with specified IP Address and hostname : gfg.com/105.22.223.186
```

**智能着装—实例方法:**

InetAddress 类有很多可以使用对象调用的实例方法。实例方法有–

<figure class="table">

| way | **Description** |
| --- | --- |
| 等于(对象对象) | This function compares this object with the specified object. |
| GetAddress() | This method returns the original IP address of this InetAddress object in bytes. |
| getcanonical hostname() | This method returns the fully qualified domain name of this IP address. |
| getHostAddress() | This method gets the IP address as a string. |
| getHostName() | This method returns the host name of this IP address. |
| hashCode() | This method gets the hashCode of this IP address. |
| 是 y Aldous dresses() | This method utility routine checks whether InetAddress is an unpredictable address. |
| islinklocaldaddress() | This method utility routine checks whether the address is not linked to the local unicast address. |
| isloop 回地址() | This method is used to check whether InetAddress represents a loopback address. |
| isMCGlobal() | This method utility routinely checks whether this address has a global multicast address. |
| IsmtleLocal() | This method utility routinely checks whether this address has a multicast address of link local scope. |
| ismcnodeloc() | This method utility routinely checks whether the multicast address has a node range. |
| isMCOrgLocal() | This method utility routinely checks whether the multicast address has an organizational scope. |
| isMCSiteLocal() | This method utility routinely checks whether the multicast address has a site range. |
| IsMultiCastAddress() | This method checks whether there are multiple servers in the site. |
| isrecharble(内部超时) | This method tests whether the address is reachable. |
| 朱庇特·朱庇特·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹·阿齐兹(签名)(NetworkInterface netif，int ttl，int timeout) | This method tests whether the address is reachable. |
| issiteoladdress() | This method utility routinely checks whether InetAddress is the local address of the site. |
| toString() | This method converts and returns an IP address as a string. |

</figure>

下面是 InetAddress 类的 Java 实现，演示了实例方法的使用–

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;
import java.net.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
        throws UnknownHostException
    {

        InetAddress address1
            = InetAddress.getByName("45.22.30.39");
        InetAddress address2
            = InetAddress.getByName("45.22.30.39");
        InetAddress address3
            = InetAddress.getByName("172.19.25.29");

        // true, as clearly seen above
        System.out.println(
            "Is Address-1 equals to Address-2? : "
            + address1.equals(address2));
        // false
        System.out.println(
            "Is Address-1 equals to Address-3? : "
            + address1.equals(address3));

        // returns IP address
        System.out.println("IP Address : "
                           + address1.getHostAddress());
        // returns host name,
        // which is same as IP
        // address in this case
        System.out.println(
            "Host Name for this IP Address : "
            + address1.getHostName());

        // returns address in bytes
        System.out.println("IP Address in bytes : "
                           + address1.getAddress());

        // false, as the given site
        //  has only one server
        System.out.println("Is this Address Multicast? : "
                           + address1.isMulticastAddress());

        System.out.println("Address in string form : "
                           + address1.toString());

        // returns fully qualified
        // domain name for this IP address.
        System.out.println(
            "Fully qualified domain name for this IP address : "
            + address1.getCanonicalHostName());

        // hashcode for this IP address.
        System.out.println("Hashcode for this IP address : "
                           + address1.hashCode());

        // to check if the InetAddress is
        // an unpredictable address..
        System.out.println(
            "Is the InetAddress an unpredictable address? : "
            + address1.isAnyLocalAddress());
    }
}
```

**Output**

```java
Is Address-1 equals to Address-2? : true
Is Address-1 equals to Address-3? : false
IP Address : 45.22.30.39
Host Name for this IP Address : 45.22.30.39
IP Address in bytes : [B@579bb367
Is this Address Multicast? : false
Address in string form : 45.22.30.39/45.22.30.39
Fully qualified domain name for this IP address : 45.22.30.39
Hashcode for this IP address : 756424231
Is the InetAddress an unpredictable address? : false
```