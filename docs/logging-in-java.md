# 登录 Java

> 原文:[https://www.geeksforgeeks.org/logging-in-java/](https://www.geeksforgeeks.org/logging-in-java/)

Java 提供了捕获日志文件的能力。

**需要日志捕获**
我们可能需要捕获应用程序活动的原因有多种。

*   记录程序中可能发生的异常情况或错误
*   获取应用程序中的信息

从日志中可以获得的细节可能有所不同。有时，我们可能需要很多关于这个问题的细节，或者有时只需要一些简单的信息。
就像当应用程序正在开发中，并且处于测试阶段时，我们可能需要捕捉很多细节。

**日志级别**
日志级别控制日志详细信息。它们决定日志文件生成的深度。每个级别都与一个数值相关联，有 7 个基本日志级别和 2 个特殊日志级别。
我们需要指定期望的日志记录级别，每次我们都寻求与日志系统进行交互。基本的日志记录级别是:

| 水平 | 价值 | 用于 |
| 严峻的 | One thousand | 表示一些严重的故障 |
| 警告 | Nine hundred | 潜在问题 |
| 信息 | eight hundred | 一般信息 |
| 配置 | Seven hundred | 配置信息 |
| 很好 | Five hundred | 一般开发者信息 |
| 好的 | four hundred | 详细的开发者信息 |
| 好的 | Three hundred | 专业开发人员信息 |

当发生了可怕的事情，应用程序无法继续运行时，就会出现严重问题。比如数据库不可用，内存不足。

每当用户给出错误的输入或凭证时，都可能出现警告。
信息供管理员或高级用户使用。它主要表示导致应用程序状态改变的操作。
配置信息可能像应用运行在什么 CPU 上，磁盘和内存空间有多少。

精细和最精细提供追踪信息。我们的应用程序中正在发生/已经发生的事情。

FINE 显示其中最重要的消息。

FINER 输出详细的跟踪消息，可能包括记录关于方法进入、退出、抛出异常的调用。

FINEST 提供高度详细的追踪消息。

此外，还有两个特殊的日志记录级别

| 离开 | 整数。最大值 | 一无所获 |
| 全部 | 整数。最小值 | 捕捉一切 |

捕捉一切可能意味着每个字段声明、定义、每个方法调用、执行的每个赋值等等。

**Java 的日志系统**
日志系统集中管理。只有一个应用程序范围的日志管理器管理日志系统的配置和进行实际日志记录的对象。
日志管理器类提供了一个与日志文件交互的全局实例。它有一个静态方法，名为 *getLogManager*

**记录器类**
记录器类提供记录的方法。因为日志管理器是进行实际日志记录的管理器，所以使用*日志管理器*的 getLogger 方法来访问它的实例。
通过记录器类的静态字段“全局 _ 记录器 _ 名称”访问全局记录器实例。它是为了方便临时使用日志包而提供的。

```java
// Java program to illustrate logging in Java
// The following code shows a basic example how logging 
// works in Java
import java.io.IOException;
import java.util.logging.Level;
import java.util.logging.Logger;
import java.util.logging.*;

class DemoLogger {
    private final static Logger LOGGER = 
                Logger.getLogger(Logger.GLOBAL_LOGGER_NAME);

    // Get the Logger from the log manager which corresponds 
    // to the given name <Logger.GLOBAL_LOGGER_NAME here>
    // static so that it is linked to the class and not to
    // a particular log instance because Log Manage is universal
    public void makeSomeLog()
    {
        // add some code of your choice here
        // Moving to the logging part now
        LOGGER.log(Level.INFO, "My first Log Message");

        // A log of INFO level with the message "My First Log Message"
    }
}

public class GfG {
    public static void main(String[] args)
    {
        DemoLogger obj = new DemoLogger();
        obj.makeSomeLog();

        // Generating some log messages through the 
        // function defined above
        LogManager lgmngr = LogManager.getLogManager();

        // lgmngr now contains a reference to the log manager.
        Logger log = lgmngr.getLogger(Logger.GLOBAL_LOGGER_NAME);

        // Getting the global application level logger 
        // from the Java Log Manager
        log.log(Level.INFO, "This is a log message");

        // Create a log message to be displayed
        // The message has a level of Info
    }
}
```

输出；

```java
May 12, 2018 7:56:33 AM DemoLogger makeSomeLog
INFO: My first Log Message
May 12, 2018 7:56:33 AM GfG main
INFO: This is a log message

```