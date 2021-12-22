# 【Java 线程和操作系统线程的区别

> 原文:[https://www . geesforgeks . org/Java-threads 和-os-threads 之间的区别/](https://www.geeksforgeeks.org/difference-between-java-threads-and-os-threads/)

多线程是一种 Java 特性，它允许同时执行程序的两个或多个部分，以最大限度地利用 CPU。这种程序的每个部分都称为线程。因此，线程是进程中的轻量级进程。

主要区别在于，同一进程内的线程在共享内存空间中运行，而进程在不同的内存空间中运行。线程是进程内的执行路径。一个进程可以包含多个线程。现在让我们讨论一下 java 线程和 OS 线程之间的区别。在这里，首先我们将定义两者，同时提供一个程序的帮助，在那里我们可以更好地理解，最后我们将以表格的方式列出它们之间的差异。

**Java 线程 vs OS 线程**

![](img/e4c85b7d82d0308dc2da0fbfb549a597.png) ![](img/8697f8efade2b6dd7aba8e328d84c0df.png)

<figure class="table">

| 要点 | 线程数 | Java 线程 |
| --- | --- | --- |
| 定义 | 线程是可以在操作系统中执行的最小处理单元 | 在 Java 环境中，线程是执行程序时遵循的路径 |
| 最小线程数 | 一个进程可以包含多个线程。 | Java 程序至少有一个线程，称为主线程 |
| 类型 | 用户级线程和内核级线程 | 用户线程和守护线程。 |
| 创建者/管理者 | 操作系统 | 当主线程调用 main()方法时，程序启动时的 Java 虚拟机(JVM)。 |
| 沟通 | 线程可以共享公共数据&通信更容易。 | wait()、notifyAll()是用于线程通信的方法。 |
| 线程调度 | 1)应用程序开发人员通过轻量级进程(LWP)将用户级线程(ULT)调度到内核级线程(KLT)。2)由系统调度器调度内核级线程，以执行不同的独特操作系统功能。 | java 中的线程调度器是 JVM 中决定哪个线程应该运行的部分。类型:1)优先调度，2)时间分片。 |
| 同步 | 实现线程同步最流行的方法是使用互斥锁。 | 使用监视器实现，使用同步块同步。 |
| 使用模型实现 | 多对一，一对一，多对多 | 绿色线程模型(多对一模型)、本地线程模型(多对多模型) |
| 死锁检测 | 1)如果资源只有一个实例2)如果有多个资源实例 | 1)嵌套同步块或试图获取不同对象的锁，或从另一个同步方法调用同步方法2)使用 io 门户。它允许我们上传一个线程转储并分析它。3)也可以使用 jConsole 或 VisualVM 来检测死锁

 |
| 避免死锁 | 可以用银行家算法完成。 | 1)避免不必要的锁定2)避免嵌套锁3)使用线程连接()方法4)使用锁排序5)锁定超时 |

</figure>

**还有，看看不同的线程状态:**

![](img/3a08411c21d776aeccbd1ee2685cba1c.png)

操作系统中线程的状态

![](img/08fcd1e73677af23c3764ffe2db2d888.png)

线程在任何时刻的各种状态

> **注意:**从 1.3 版本开始，Linux 的 Sun JVM 中放弃了绿色线程，使用由 OS 管理的本机线程。详见[本](https://stackoverflow.com/questions/5713142/green-threads-vs-non-green-threads)。