# Java 中的 LogManager reset()方法，示例

> 原文:[https://www . geesforgeks . org/log manager-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-reset-method-in-java-with-examples/)

**Java . util . logging . log manager**的 **reset()** 方法用于重置日志配置。如果出现异常情况，此方法将引发 SecurityException，如下所示

**语法:**

```
public void reset() throws SecurityException

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法不返回任何东西。它只是重置日志配置。

**异常:**如果在调用方没有日志记录权限的情况下存在安全管理器，则此方法抛出以下异常:

*   **Safety exception:** .

下面程序举例说明重置()方法:

```
// Java program to illustrate
// LogManager reset() method

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

            System.out.println("Resetting the logging configuration");

            // Resetting the logging configuration
            // using reset() method
            logManager.reset();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
LogManager: java.util.logging.LogManager@1540e19d
Resetting the logging configuration
java.security.AccessControlException:
 access denied ("java.util.logging.LoggingPermission" "control")

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/util/logging/LogManager.html#reset--)