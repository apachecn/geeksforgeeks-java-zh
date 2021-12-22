# 使用进程和运行时调用 Java 中的外部程序

> 原文:[https://www . geesforgeks . org/calling-external-program-Java-use-process-runtime/](https://www.geeksforgeeks.org/calling-external-program-java-using-process-runtime/)

Java 包含通过简单的 Java 代码启动外部进程的功能——系统上的可执行文件或现有应用程序，如谷歌浏览器或媒体播放器。一种方法是使用以下两个类:进程类

*   Runtime class

java.lang 包中的 Process 类包含许多有用的方法，如终止子进程、让线程等待一段时间、返回子进程的 I/O 流等。随后，运行时类提供了一个与 Java 运行时环境交互的入口。它包含执行进程的方法，给出可用处理器的数量，显示 JVM 中的空闲内存，等等。

```
// A sample Java program (Written for Windows OS)
// to demonstrate creation of external process 
// using Runtime and Process
class CoolStuff
{
    public static void main(String[] args)
    {
        try
        {
            // Command to create an external process
            String command = "C:\Program Files (x86)"+
                 "\Google\Chrome\Application\chrome.exe";

            // Running the above command
            Runtime run  = Runtime.getRuntime();
            Process proc = run.exec(command);
        }

        catch (IOException e)
        {
            e.printStackTrace();
        }
    }
}
```

Runtime.getRuntime()只是返回与当前 Java 应用程序关联的 Runtime 对象。可执行路径是在 process exec(字符串路径)方法中指定的。我们还有一个 IOException try-catch 块来处理找不到要执行的文件的情况。运行代码时，谷歌浏览器的一个实例会在计算机上打开。

创建外部流程的另一种方法是使用[流程构建器](http://docs.oracle.com/javase/6/docs/api/java/lang/ProcessBuilder.html)，这将在下一篇文章中讨论。[用 Java process builder 创建一个基本的在线判卷](https://www.geeksforgeeks.org/processbuilder-in-java-to-create-a-basic-online-judge/)

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。