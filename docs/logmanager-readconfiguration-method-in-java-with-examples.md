# Java 中的 LogManager readConfiguration()方法，带示例

> 原文:[https://www . geesforgeks . org/log manager-read configuration-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-readconfiguration-method-in-java-with-examples/)

**Java . util . logging . logmanager**的 **readConfiguration()** 方法用于读取和初始化默认配置。如果异常情况发生，该方法将抛出 IOException 和 SecurityException，如下所示

**语法:**

```
public void readConfiguration()
  throws IOException, SecurityException
```

**参数:**该方法不接受任何参数。
**返回值:**这个方法不返回任何东西。它只是读取并初始化日志配置。
**异常:**该方法抛出以下异常:

*   **IO 异常:**如果读取配置时出现任何 IO 错误。
*   **安全性异常:**如果在调用方没有日志记录权限的情况下存在安全管理器。

以下程序说明了 readConfiguration()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// LogManager readConfiguration() method

import java.util.logging.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {
            // Create LogManager object
            LogManager logManager
                = LogManager.getLogManager();

            System.out.println("LogManager: "
                               + logManager);

            System.out.println(
                "Reading the configuration "
                + "using readConfiguration() method");
            logManager.readConfiguration();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:** LogManager: java.util.logging.LogManager@1540e19d Reading the configuration using readConfiguration() method java.security.AccessControlException: access denied (“java.util.logging.LoggingPermission” “control”)  

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # read configuration–T4】