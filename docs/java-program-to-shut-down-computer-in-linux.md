# 在 Linux 中关闭计算机的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到关闭-linux 中的计算机/](https://www.geeksforgeeks.org/java-program-to-shut-down-computer-in-linux/)

在这个程序中，如果操作系统是 Linux，我们将关闭计算机。因此，首先我们将检查运行 Java 程序的系统是否是 Linux。如果操作系统不是 Linux，那么我们就不会继续打印“不支持的操作系统”。如果它是一个 Linux 操作系统，那么用户将输入时间(以秒为单位)，以便在此时间之后电脑将关闭。

这里的时间(秒)不包括您的系统关闭所花费的时间。例如:如果用户将输入 1 秒钟，那么它包括 1 秒钟加上关闭系统所需的时间。这是因为由于系统架构、RAM 的可用性等原因。影响关机速度。

**进场:**

1.  导入必需的包。
2.  检查你的电脑是否有 Linux 操作系统。
3.  如果不是 Linux，则打印“不支持的操作系统”。
4.  如果是 Linux，向用户输入“多少秒后电脑将关闭”。
5.  电脑将关闭。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Shut Down Computer
// when Operating System is Linux.

import java.io.IOException;
import java.util.Scanner;

public class SystemShutDown {

    public static void main(String args[])
        throws IOException
    {
        // Initialized to  take input from user in seconds
        int seconds;

        // Find Out Operating System
        String operatingSystem
            = System.getProperty("os.name");

        // Print Operating System of Computer
        System.out.println("Name of Operating System:"
                           + operatingSystem);

        // Check if Computer Operating System is Linux or
        // not
        if (operatingSystem.equals("Linux")) {

            // Returns the runtime object associated with
            // the current Java application.
            Runtime runTime = Runtime.getRuntime();

            // Take input from user in seconds
            seconds = 5;

            // Retrieve current Runtime Environment
            Process processing
                = runTime.exec("shutdown -h -t " + seconds);

            // Shutting Down the System
            System.exit(0);
        }
```

**输出:**

```
Name of Operating System:Linux  
//Shutting Down your Linux system
```