# 获取 Windows 和 Linux 机器系统主板序列号的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-system-母板-序列号-for-windows-and-Linux-machine/](https://www.geeksforgeeks.org/java-program-to-get-system-motherboard-serial-number-for-windows-and-linux-machine/)

主板是整个中央处理器架构的基础。主要是印刷电路板负责连接硬盘、中央处理器、外部端口等所有主要组件。一个好的有知识的计算机用户必须知道他们的主板的制造商、版本和序列号。本文主要围绕编写 Java 代码来为用户的相应机器提取主板的序列号。序列号对于每个主板都是唯一的，因此每个用户在运行相同的程序时会得到不同的输出。下面，我们提供了代码来找出 Windows 和 Linux 机器主板的序列号。

**A. Linux 机器:**

检索主板序列号的主要概念是使用 Java 代码在终端中运行命令，并将检索到的序列号存储为字符串，然后打印在屏幕上。

**算法:**

1.  首先，我们将应该在终端上运行的命令存储在一个名为 command 的变量中。
2.  接下来，我们通过调用用于与 Java 运行时环境交互的 Java 运行时类来初始化一个进程。
3.  我们将命令作为参数传递给 exec 函数，该函数的主要功能是执行命令。
4.  对于下一步，我们使用 java 输入/输出包的 InputStreamReader 类从流程中捕获输入流。
5.  然后，使用 BufferedReader 类从 InputStreamReader 中读取流。
6.  我们把它存储在一个变量中。
7.  接下来，我们等待进程终止。
8.  我们关闭了缓冲恐惧。
9.  在 catch 块中，如果出现错误，我们将打印堆栈跟踪，并将保存序列号的变量设置为空。
10.  最后，我们返回这个变量，并使用驱动程序代码打印输出。

**使用的命令:**

```
sudo dmidecode -s baseboard-serial-number
```

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to get the system
// motherboard serial number on linux

// importing the libraries
import java.io.*;

class GFG {
    static String getLinuxMotherBoardSerialNumber()
    {

        // command to be executed on the terminal
        String command
            = "sudo dmidecode -s baseboard-serial-number";

        // variable to store the Serial Number
        String serialNumber = null;

        // try block
        try {

            // declaring the process to run the command
            Process SerialNumberProcess
                = Runtime.getRuntime().exec(command);

            // getting the input stream using
            // InputStreamReader using Serial Number Process
            InputStreamReader ISR = new InputStreamReader(
                SerialNumberProcess.getInputStream());

            // declaring the Buffered Reader
            BufferedReader br = new BufferedReader(ISR);

            // reading the serial number using
            // Buffered Reader
            serialNumber = br.readLine().trim();

            // waiting for the system to return
            // the serial number
            SerialNumberProcess.waitFor();

            // closing the Buffered Reader
            br.close();
        }

        // catch block
        catch (Exception e) {

            // printing the exception
            e.printStackTrace();

            // giving the serial number the value null
            serialNumber = null;
        }

        // returning the serial number
        return serialNumber;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // printing and calling the method which
        // returns the Serial Number
        System.out.println(
            getLinuxMotherBoardSerialNumber());
    }
}
```

**输出:**

```
PGPPP018J940BP
```

**B. Windows 机:**

用于在 Windows 机器上检索主板序列号的代码与用于在 Linux 机器上检索主板序列号的代码的唯一区别在于所使用的命令。剩下的算法和代码保持不变。

**使用的命令:**

```
wmic baseboard get serialnumber
```

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to get the system
// motherboard serial number on Windows

// importing the libraries
import java.io.*;

class GFG {
    static String getWindowsMotherBoardSerialNumber()
    {

        // command to be executed on the terminal
        String command = "wmic baseboard get serialnumber";

        // variable to store the Serial Number
        String serialNumber = null;

        // try block
        try {

            // declaring the process to run the command
            Process SerialNumberProcess
                = Runtime.getRuntime().exec(command);

            // getting the input stream using
            // InputStreamReader using Serial Number Process
            InputStreamReader ISR = new InputStreamReader(
                SerialNumberProcess.getInputStream());

            // declaring the Buffered Reader
            BufferedReader br = new BufferedReader(ISR);

            // reading the serial number using
            // Buffered Reader
            serialNumber = br.readLine().trim();

            // waiting for the system to return
            // the serial number
            SerialNumberProcess.waitFor();

            // closing the Buffered Reader
            br.close();
        }

        // catch block
        catch (Exception e) {

            // printing the exception
            e.printStackTrace();

            // giving the serial number the value null
            serialNumber = null;
        }

        // returning the serial number
        return serialNumber;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // printing and calling the method which
        // returns the Serial Number
        System.out.println(
            getWindowsMotherBoardSerialNumber());
    }
}
```

**输出:**

```
PGPPP018J940BP
```