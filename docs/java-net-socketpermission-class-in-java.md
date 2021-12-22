# java 中的 java.net.SocketPermission 类

> 原文:[https://www . geesforgeks . org/Java-net-socketpermission-class-in-Java/](https://www.geeksforgeeks.org/java-net-socketpermission-class-in-java/)

java.net.SocketPermisson 类表示您是否有权通过套接字访问网络。SocketPermission 由一个主机和一组操作组成。

**类申报:**

```java
public final class SocketPermission
extends Permission
implements Serializable
```

**构造函数:**

<figure class="table">

| Constructor | Description |
| --- | --- |
| ManagementPermission (string name) | This will construct a management permission with the specified name. |
| ManagementPermission | This will construct a new management permission object. |

</figure>

**公共套接字权限(字符串主机，字符串操作):**

用于创建具有指定操作的 SocketPermission 类的新对象。

**方法:**

<figure class="table">

| way | Description |
| --- | --- |
| equals (object obj) | It checks whether two SocketPermission objects are equal. |
| GetActions () | It returns the operation |
| Hashcode () | of this SocketPermission object in string format. |
| Implication (Permission p) | Check whether this SocketPermssion object implies this permission. |
| New Permission Collection () | It returns a new Permission Collection object. |

</figure>

**示例:**

## Java

```java
// Java Program to show the usage of
// java.net.SocketPermission Class
import java.io.IOException;
import java.net.SocketPermission;
import java.security.Permission;
import java.security.PermissionCollection;

public class Socket {

    public static void main(String args[])
    {
        try {
            // getting permission object
            Permission p = getPermission();

            // print actions of permission p
            System.out.println(p.getActions());

            // printing hashcode value of permission p
            System.out.println(p.hashCode());

            // creating a permissionCollection object and
            // printing it
            PermissionCollection p1
                = p.newPermissionCollection();
            System.out.print(p1);
        }
        catch (Exception e) {
            System.err.print("Permission denied");
        }
    }
    public static Permission getPermission()
        throws IOException
    {
        int port = 3000;
        String host = "localhost";
        return new SocketPermission(host + ":" + port,
                                    "Connect,resolve");
    }
}
```

**输出**

```java
connect,resolve
-1204607085
java.net.SocketPermissionCollection@30dae81 (
)
```