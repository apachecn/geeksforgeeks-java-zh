# Java 中的 Logger finer()方法，示例

> 原文:[https://www . geesforgeks . org/logger-finer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logger-finer-method-in-java-with-examples/)

用于记录更精细消息的**记录器**类的**更精细()**方法。此方法用于将 FINER 类型日志传递给所有注册的输出处理程序对象。

**FINER 消息:** FINER 输出详细的跟踪消息，可能包括记录关于方法进入、退出、抛出异常的调用。

根据传递的参数数量，有两种类型的 finer()方法。

1.  **finer(字符串 msg)** :此方法用于记录 finer 消息。如果记录器被启用来记录更精细级别的消息，那么给定的消息将被转发到所有注册的输出处理程序对象。

**语法:**

```java
public void finer(String msg)

```

**参数:**该方法接受单个参数字符串，即字符串消息。

**返回值:**此方法不返回任何内容。

下面的程序说明了更好的(字符串消息)方法:

**程序 1:**

```java
// Java program to demonstrate
// Logger.finer(String msg) method

import java.io.IOException;
import java.util.logging.*;

public class GFG {

    public static void main(String[] args)
        throws SecurityException, IOException
    {

        // Create a Logger
        Logger logger
            = Logger.getLogger(
                GFG.class.getName());

        // Create a file handler object
        FileHandler handler
            = new FileHandler("logs.txt");
        handler.setFormatter(new SimpleFormatter());

        // Add file handler as
        // handler of logs
        logger.addHandler(handler);

        // Set Logger level()
        logger.setLevel(Level.FINER);

        // Call finer method
        logger.finer("Welcome geeks");
    }
}
```

logs.txt 文件上打印的输出如下所示。
**输出:**
![](img/f142514e1cea476fca9469f42a25561f.png)

*   **finer(Supplier msgSupplier)**: This method is used Log a FINER message, constructed only if the logging level is such that the message will actually be logged. It means If the logger is enabled for the FINER message level then the message is constructed by invoking the provided supplier function and forwarded to all the registered output Handler objects.

    **语法:**

    ```java
    public void finer(Supplier msgSupplier)

    ```

    **参数:**该方法接受单个参数**msgssupplier**，这是一个函数，当调用该函数时，会产生所需的日志消息。

    **返回值:**此方法不返回任何内容。

    以下程序说明了更好的方法:
    **程序 1:**

    ```java
    // Java program to demonstrate
    // Logger.finer(Supplier<String>) method

    import java.io.IOException;
    import java.util.function.Supplier;
    import java.util.logging.*;

    public class GFG {

        public static void main(String[] args)
            throws SecurityException, IOException
        {

            // Create a Logger
            Logger logger
                = Logger.getLogger(
                    GFG.class.getName());

            // Create a file handler object
            FileHandler handler
                = new FileHandler("logs.txt");
            handler.setFormatter(
                new SimpleFormatter());

            // Add file handler as
            // handler of logs
            logger.addHandler(handler);

            // Set Logger level()
            logger.setLevel(Level.FINER);

            // Create a supplier<String> method
            Supplier<String> StrSupplier
                = () -> new String("SET KEY=VALUE");

            // Call finer(Supplier<String>)
            logger.finer(StrSupplier);
        }
    }
    ```

    log.txt 上打印的输出如下所示。
    **输出:**
    ![](img/c67d17d66d9c15ef9fa0c2e2edda32f1.png)

    **参考文献:**

    *   [https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logger . html # finer(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Logger.html#finer(java.lang.String))
    *   [https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logger . html # finer(Java . util . function . supplier)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Logger.html#finer(java.util.function.Supplier))