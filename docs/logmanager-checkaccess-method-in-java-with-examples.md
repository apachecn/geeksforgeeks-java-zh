# Java 中的 LogManager checkAccess()方法，示例

> 原文:[https://www . geesforgeks . org/log manager-check access-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-checkaccess-method-in-java-with-examples/)

**Java . util . logging . logmanager**的 **checkAccess()** 方法用于检查该上下文是否有权限修改日志配置，需要 LoggingPermission(“控制”)。如果出现异常情况，此方法将引发 SecurityException，如下所示

**语法:**

```
public void checkAccess()
  throws SecurityException

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法不返回任何东西。它只是检查这个上下文是否有权限修改日志配置。

**异常:**如果在调用方没有日志记录权限的情况下存在安全管理器，则此方法抛出以下异常:

*   **Safety exception:** .

下面程序说明 checkAccess()方法:

```
// Java program to illustrate
// LogManager checkAccess() method

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
                "Checking for permissions\n");

            // Checking for permissions
            // using checkAccess() method
            logManager.checkAccess();
        }
        catch (SecurityException e) {
            System.out.println("Permission Denied");
        }
    }
}
```

**输出:**

```
LogManager: java.util.logging.LogManager@1540e19d
Checking for permissions

Permission Denied

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # checkAccess–](https://docs.oracle.com/javase/9/docs/api/java/util/logging/LogManager.html#checkAccess--)