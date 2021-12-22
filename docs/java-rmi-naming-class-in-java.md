# Java . RMI . Java 中的命名类

> 原文:[https://www . geesforgeks . org/Java-RMI-naming-class-in-Java/](https://www.geeksforgeeks.org/java-rmi-naming-class-in-java/)

[*Java.rmi.Naming*](https://www.geeksforgeeks.org/how-to-run-java-rmi-application/) 类包含一个方法，用于绑定、解除绑定或重新绑定远程注册表中存在的远程对象的名称。此类还用于获取远程注册表中存在的对象的引用或与此注册表关联的名称列表。

**语法:**类声明

```java
public final class Naming extends Object
```

让我们讨论一下这门课的一些主要方法，如下所示:

最常用的方法描述如下:

1.  *bind()*
2.  *列表()*
3.  *查找()*
4.  *rebind()*
5.  *解除绑定()*

**方法 1:** 绑定()

**语法:**

```java
static void bind(String name, remote object)
// Bind this name with this remote object
```

**参数:**远程注册表的名称

**异常:**

1.  Bound When the name is bound
2.  [Exception](https://www.geeksforgeeks.org/url-class-java-examples/) When the format of name is not URL
3.  [Remote Exception](https://www.geeksforgeeks.org/remote-method-invocation-in-java/) An exception occurred when contacting the remote registry failed.
4.  Exception occurred when access to this operation is not allowed.

**方法二:** *列表()* 用于获取列表中与注册表关联的名称

**语法:**

```java
static string[] list(String name)
```

**参数:**远程注册表的名称

**返回类型:**与此注册表绑定的名称数组

**异常:**

1.  [Exception occurs when the format of the name is not the website address](https://www.geeksforgeeks.org/url-class-java-examples/)
2.  [A remote exception occurred when the contact with the remote registry failed](https://www.geeksforgeeks.org/remote-method-invocation-in-java/)

**方法 3:** *查找()*查找与该名称关联的远程对象的引用

**语法:**

```java
static remote lookup(String name)
```

**参数:**远程注册表的名称

**返回类型:**远程对象的引用

异常:

1.  NotBoundException occurs when the name is not bound to the current operation.
2.  RemoteException occurs when the contact with the remote registry fails.
3.  AccessException occurs when access to this operation is not allowed.
4.  MalformedURLException occurs when the format of the name is not URL.

**方法 4:** rebind()方法将此名称与关联的远程对象重新绑定

**语法:**

```java
static void rebind(String name, remote object)
```

**参数:**取两个参数，即名称和对象。

*   The name of the remote registry
*   The name of the remote object to associate with.

**异常:**

1.  当名称的格式不是网址时，就会出现异常
2.  当与远程注册表的联系失败时，会出现远程异常
3.  当不允许访问此操作时，会出现访问异常

**方法 5:** *解除绑定()*解除此名称与关联远程对象的绑定

**语法:**

```java
static void unbind(String name) 
```

**参数:**远程注册表的名称

**异常:**

1.  Unbounded exceptions occur when the name is not bound to the current operation.
2.  Exception occurs when the format of name is not URL.
3.  The remote exception occurs when the contact with the remote registry fails.
4.  An access exception occurs when access to this operation is not allowed.

**例 1:**

## 爪哇

```java
// Java Program to create a registry
// Server's Side

// Importing java.rmi package to enable object of one JVM
// to invoke methods on object in another JVM
import java.rmi.*;
import java.rmi.AlreadyBoundException;
import java.rmi.Naming;
import java.rmi.NotBoundException;
import java.rmi.Remote;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import java.rmi.server.*;

// Interface
// creating remote interface
interface demo extends Remote {
    public String msg(String msg) throws RemoteException;
}

// Class 1
// Helper Class
class demoRemote
    extends UnicastRemoteObject implements demo {
    demoRemote() throws RemoteException { super(); }

    // @Override
    public String msg(String msg) throws RemoteException
    {
        // Display message only
        System.out.println("GeeksForGeeks");
        return null;
    }
}

// Class 2
// Main class
public class GFG_Server {

    // Main driver method
    public static void main(String args[])
        throws RemoteException, NotBoundException,
               AlreadyBoundException
    {

        // Try block to check for exceptions
        try {

            // Creating a new registry by creating
            // an object of Registry class
            Registry registry
                = LocateRegistry.createRegistry(3000);

            demo obj = new demoRemote();

            // binding obj to remote registry
            Naming.bind("rmi://localhost:3000"
                            + "/geeksforgeeks",
                        (Remote)obj);

            // Display message when program
            // is executed succussfully
            System.out.println(
                "registry created successfully");
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Getting the name of the exception using
            // the toString() method over exception object
            System.err.println(e.toString());
        }
    }
}
```

**输出:**

```java
registry created successfully
```

**实现:**寻找对象的 Java 程序(客户端)

**例 2:**

## 爪哇

```java
// Java Program to look for the object
// Client Side

// Importing java.rmi package to enable object of one JVM
// to invoke methods on object in another JVM
import java.rmi.*;

// Main class
public class GFG_Client {

    // Main driver method
    public static void main(String args[])
    {
        // try block to check for exceptions
        try {

            // Looking for object in remote registry
            demo client = (demo)Naming.lookup(
                "rmi://localhost:3000/obj");

            // Print and display the client message
            System.out.println(client.msg());
        }

        // Catch block to handle the exception
        catch (Exception e) {
        }
    }
}
```

**输出:**

```java
GeeksForGeeks
```