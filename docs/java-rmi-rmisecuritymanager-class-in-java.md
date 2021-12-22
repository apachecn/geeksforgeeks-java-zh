# java 中的 Java . RMI . rmsecuritymanager 类

> 原文:[https://www . geeksforgeeks . org/Java-RMI-rmsecuritymanager-class-in-Java/](https://www.geeksforgeeks.org/java-rmi-rmisecuritymanager-class-in-java/)

**rmsecuritymanager**通过覆盖来自 **SecurityManager** 的所有相关访问检查方法，为作为远程对象存根加载的类实施安全策略。默认情况下，存根对象只允许执行类定义和类访问操作。

> **注:**
> 
> *   如果本地安全管理器不是使用 System.setSecurityManager()方法的 RMISecurityManager
> *   那么存根类只能从本地文件系统加载。

```
java.lang.Object
java.lang.SecurityManager
java.rmi.RMISecurityManager
```

**语法:**

```
*public class RMISecurityManager* 
*extends SecurityManager*
```

> **注意:**使用下载代码的 RMI 应用程序使用的 SecurityManager 的一个子类。

如果没有设置安全管理器，RMI 的类加载器将不会从远程位置下载任何类。RMISecurityManager 不适用于在浏览器安全管理器保护下运行的小程序。RMISecurityManager 实现的策略与 SecurityManager 实现的策略没有什么不同。因此，RMI 应用程序应该使用 SecurityManager 类或另一个特定于应用程序的 SecurityManager 实现，而不是这个类。

**如何纳入安全经理课程？**

要在应用程序中使用 SecurityManager，请在代码中添加以下语句(它需要在 RMI 可以从远程主机下载代码之前执行，因此它很可能需要出现在应用程序的主方法中)

**语法:**

```
System.setSecurityManager(new SecurityManager());
```

RMISecurityManager 实现的策略与 SecurityManager 实现的策略相同。RMI 应用程序应该使用 SecurityManager 类或另一个适当的 SecurityManager 实现来代替这个类。只有在设置了安全管理器的情况下，RMI 的类加载器才会从远程位置下载类。

现在让我们按照下面的方式继续这个类的构造函数:

*   **rmsecuritymanager()**:构造一个新的 rmsecuritymanager

**实施:**

```
if (System.getSecurityManager() == null) 
{
    // Setting the RMISecurityManager on System
    System.setSecurityManager(new SecurityManager());
} 
```

小程序通常在已经有安全管理器的容器中运行，因此小程序通常不需要设置安全管理器。如果您有一个独立的应用程序，您可能需要设置一个 SecurityManager 来启用类下载。这可以通过在代码中添加以下内容来实现。(它需要在 RMI 可以从远程主机下载代码之前执行，所以它很可能需要出现在您的应用程序的主方法中，从下图中可以更好地理解这一点。

插图 1:

```
// Protected synchronized method
protected static synchronized void setSecurityManager() 
{
    if (System.getSecurityManager() == null) 
    {
        // Setting the RMISecurityManager on System
        System.setSecurityManager(new RMISecurityManager());
    }
}
```

**插图 2:**

```
// Synchronized method
synchronized static void ensureSecurityManager() 
{
    if (System.getSecurityManager() == null) 
    {
        // Setting the RMISecurityManager on System
        System.setSecurityManager(new RMISecurityManager());
    }
}
```

**插图 3:**

```
// Protected synchronized method
protected static synchronized void setSecurityManager() 
{
    if (System.getSecurityManager() == null) 
    {
        // Setting the RMISecurityManager on System
        System.setSecurityManager(new RMISecurityManager());
    }
}
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate RMISecurityManager Class
// Via creating Registry and Rebinding Service

// Importing required classes
import java.lang.Object;
import java.lang.SecurityManager;
import java.rmi.RMISecurityManager;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Try block to check for exceptions
        try {

            // Setting the RMISecurityManager on System
            System.setSecurityManager(
                new RMISecurityManager());
            RmiService service = new RmiServiceImpl();

            // First we will be creating registry
            // using createRegistry() method
            LocateRegistry.createRegistry(6600);

            // Now rebinding the service
            // using rebind method
            Naming.rebind(
                "rmi://127.0.0.1:6600/PersonService",
                service);

            // Display message on the console for
            // successful execution of the program
            System.out.println("Service Start!");
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Printing the line number where exception
            // occured using printStackTrace() method
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
Service Start!
```

在控制台上，我们将显示如上所示的消息。