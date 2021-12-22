# Java 中的 Java.lang.ProcessBuilder 类

> 原文:[https://www . geesforgeks . org/Java-lang-process builder-class-Java/](https://www.geeksforgeeks.org/java-lang-processbuilder-class-java/)

此类用于创建操作系统进程。每个流程构建器实例管理一组流程属性。start()方法用这些属性创建一个新的 Process 实例。start()方法可以从同一个实例中重复调用，以创建具有相同或相关属性的新子流程。

*   ProcessBuilder 可用于帮助创建操作系统进程。
*   在 JDK 5.0 之前，创建和执行进程的唯一方法是使用 Runtime.exec()方法。
*   它扩展了类对象。
*   此类未同步。

**施工方:**

*   **ProcessBuilder(List 命令):**用指定的操作系统程序和参数构造一个进程构建器。

*   **process builder(String…command):**这将使用指定的操作系统程序和参数构建一个进程构建器。

**方法:**

**1。List command():** 这个方法返回进程构建器的操作系统程序和参数。

```
Syntax: public List command().
Returns: this process builder's program and its arguments.
Exceptions: NullPointerException - if the argument is null.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating command() method
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {
        // creating list of process
        List<String> list = new ArrayList<String>();
        list.add("notepad.exe");

        // create the process
        ProcessBuilder build = new ProcessBuilder(list);

        // checking the command i list
        System.out.println("command: " + build.command());
    }
}
```

**Output**

```
command: [notepad.exe]
```

**2。ProcessBuilder 命令(List 命令):**此方法设置进程构建器的操作系统程序和参数。

```
Syntax: public ProcessBuilder command(List command).
Returns: NA.
Exception: NullPointerException - if the argument is null.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating ProcessBuilder
// command(List<String> command)
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {
        // creating list of process
        List<String> list = new ArrayList<String>();
        list.add("notepad.exe");
        list.add("xyz.txt");

        // create the process
        ProcessBuilder build = new ProcessBuilder(list);

        // checking the command in list
        System.out.println("command: " + build.command());
    }
}
```

**Output**

```
command: [notepad.exe, xyz.txt]
```

**3。ProcessBuilder 目录(文件目录):**此方法设置流程构建器的工作目录。随后由对象的 start()方法启动的子进程将使用它作为它们的工作目录。该参数可能为 null，这意味着使用当前 Java 进程的工作目录，通常是由 system 属性 user.dir 命名的目录，作为子进程的工作目录。

```
Syntax: public ProcessBuilder directory(File directory).
Returns: this process builder.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating directory() method
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {
        // creating list of process
        List<String> list = new ArrayList<String>();
        list.add("notepad.exe");
        list.add("abc.txt");

        // creating the process
        ProcessBuilder build = new ProcessBuilder(list);

        // setting the directory
        build.directory(new File("src"));

        // checking the directory, on which currently
        // working on
        System.out.println("directory: "
                           + build.directory());
    }
}
```

**Output**

```
directory: src
```

**4。Map environment():** 此方法返回流程构建器环境的字符串映射视图。每当创建流程构建器时，环境都会被初始化为当前流程环境的副本。随后由对象的 start()方法启动的子进程将使用这个映射作为它们的环境。

```
Syntax: public Map environment()
Returns: this process builder's environment
Exception: SecurityException - if a security manager exists 
and its checkPermission method doesn't allow access to the process environment.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating environment() method
import java.io.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {
        // creating the process
        ProcessBuilder pb = new ProcessBuilder();

        // map view of this process builder's environment
        Map<String, String> envMap = pb.environment();

        // checking map view of environment
        for (Map.Entry<String, String> entry :
             envMap.entrySet()) {
            // checking key and value separately
            System.out.println("Key = " + entry.getKey()
                               + ", Value = "
                               + entry.getValue());
        }
    }
}
```

**输出:**

```
Key = PATH, Value = /usr/bin:/bin:/usr/sbin:/sbin
Key = JAVA_MAIN_CLASS_14267, Value = ProcessBuilderDemo
Key = J2D_PIXMAPS, Value = shared
Key = SHELL, Value = /bin/bash
Key = JAVA_MAIN_CLASS_11858, Value = org.netbeans.Main
Key = USER, Value = abhishekverma
Key = TMPDIR, Value = /var/folders/9z/p63ysmfd797clc0468vvy4980000gn/T/
Key = SSH_AUTH_SOCK, Value = /private/tmp/com.apple.launchd.uWvCfYQWBP/Listeners
Key = XPC_FLAGS, Value = 0x0
Key = LD_LIBRARY_PATH, Value = /Library/Java/JavaVirtualMachines
/jdk1.8.0_121.jdk/Contents/Home/jre/lib/
amd64:/Library/Java/JavaVirtualMachines/jdk1.8.0_121.jdk
/Contents/Home/jre/lib/i386:
Key = __CF_USER_TEXT_ENCODING, Value = 0x1F5:0x0:0x0
Key = Apple_PubSub_Socket_Render, Value = /private/tmp/com.apple.launchd.weuNq4pAfF/Render
Key = LOGNAME, Value = abhishekverma
Key = LC_CTYPE, Value = UTF-8
Key = XPC_SERVICE_NAME, Value = 0
Key = PWD, Value = /
Key = SHLVL, Value = 1
Key = HOME, Value = /Users/abhishekverma
Key = _, Value = /Library/Java/JavaVirtualMachines/
jdk1.8.0_121.jdk/Contents/Home/bin/java
```

**理解上面的输出:**输出是子流程构建的地图视图。以上输出因用户而异，完全取决于操作系统和用户。

**5。boolean redirecterrortstream():**这个方法告诉流程构建器是否合并标准错误和标准输出。如果此属性为真，则由对象的 start()方法随后启动的子进程生成的任何错误输出都将与标准输出合并，以便可以使用 Process.getInputStream()方法读取两者。这使得将错误消息与相应的输出相关联变得更加容易。初始值为假。

```
Syntax: public boolean redirectErrorStream().
Returns: this process builder's redirectErrorStream property.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating redirectErrorStream() method
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {

        // creating list of commands
        List list = new ArrayList();

        list.add("notepad.exe");
        list.add("xyz.txt");

        // creating the process
        ProcessBuilder build = new ProcessBuilder(list);

        // checking if error stream is redirected
        System.out.println(build.redirectErrorStream());
    }
}
```

**输出:**

```
false
```

**6。ProcessBuilder redirectErrorStream(布尔 redirectErrorStream):** 此方法设置此进程生成器的 redirectErrorStream 属性。如果此属性为真，则由该对象的 start()方法随后启动的子进程生成的任何错误输出都将与标准输出合并，以便可以使用 Process.getInputStream()方法读取两者。这使得将错误消息与相应的输出相关联变得更加容易。初始值为假。

```
Syntax: public ProcessBuilder redirectErrorStream(boolean redirectErrorStream).
Returns: this process builder.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating redirectErrorStream(boolean
// redirectErrorStream) method
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {

        // creating list of commands
        List list = new ArrayList();

        list.add("notepad.exe");
        list.add("xyz.txt");

        // creating the process
        ProcessBuilder build = new ProcessBuilder(list);

        // redirecting error stream
        build.redirectErrorStream(true);

        // checking if error stream is redirected
        System.out.println(build.redirectErrorStream());
    }
}
```

**输出:**

```
true
```

**流程启动():**此方法使用流程构建器的属性启动一个新流程。新进程将调用由目录()给定的工作目录中的命令()给定的命令和参数，进程环境由环境()给定。此方法检查该命令是否是有效的操作系统命令。哪些命令有效取决于系统，但至少命令必须是非空字符串的非空列表。如果有一个安全管理器，它的 checkExec 方法是用这个对象的命令数组的第一个组件作为参数来调用的。这可能会导致引发安全异常。

```
Syntax: public Process start().
Returns: a new Process object for managing the subprocess.
Exception: NullPointerException - If an element of the command list is null
IndexOutOfBoundsException - If the command is an empty list (has size 0).
SecurityException - If a security manager exists 
and its checkExec method doesn't allow creation of the subprocess.
IOException - If an I/O error occurs.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating start() method
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg) throws IOException
    {
        // creating list of commands
        List<String> commands = new ArrayList<String>();
        commands.add("ls"); // command
        commands.add("-l"); // command
        commands.add(
            "/Users/abhishekverma"); // command in Mac OS

        // creating the process
        ProcessBuilder pb = new ProcessBuilder(commands);

        // startinf the process
        Process process = pb.start();

        // for reading the output from stream
        BufferedReader stdInput
            = new BufferedReader(new InputStreamReader(
                process.getInputStream()));
        String s = null;
        while ((s = stdInput.readLine()) != null) {
            System.out.println(s);
        }
    }
}
```

**输出:**

```
total 0
drwxr-xr-x  10 abhishekverma  staff   340 Jun 20 02:24 AndroidStudioProjects
drwx------@ 22 abhishekverma  staff   748 Jun 20 03:00 Desktop
drwx------@  7 abhishekverma  staff   238 Apr 29 22:03 Documents
drwx------+ 27 abhishekverma  staff   918 Jun 20 03:01 Downloads
drwx------@ 65 abhishekverma  staff  2210 Jun 18 20:48 Library
drwx------+  3 abhishekverma  staff   102 Mar 28 13:08 Movies
drwx------+  4 abhishekverma  staff   136 Apr  8 04:51 Music
drwxr-xr-x   4 abhishekverma  staff   136 Jun 19 15:01 NetBeansProjects
drwx------+  5 abhishekverma  staff   170 Apr 10 09:46 Pictures
drwxr-xr-x+  6 abhishekverma  staff   204 Jun 18 20:45 Public
-rw-r--r--   1 abhishekverma  staff     0 Apr 15 19:23 newreactjs.jsx
```

**process builder inherio():**将子进程标准 I/O 的源和目标设置为与当前 Java 进程相同。

```
Syntax: public ProcessBuilder inheritIO().
Returns: this process builder.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating inheritIO() method
import java.io.*;
import java.lang.*;
import java.util.*;
class ProcessBuilderDemo {
    public static void main(String[] arg)
        throws IOException, InterruptedException
    {
        ProcessBuilder pb = new ProcessBuilder(
            "echo", "Hello GeeksforGeeks\n"
                        + "This is ProcessBuilder Example");
        pb.inheritIO();
        Process process = pb.start();
        process.waitFor();
    }
}
```

**输出:**

```
Hello GeeksforGeeks
This is ProcessBuilder Example
```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。