# 如何增加 Java 虚拟机中的堆大小？

> 原文:[https://www . geesforgeks . org/如何在 java 虚拟机中增加堆大小/](https://www.geeksforgeeks.org/how-to-increase-heap-size-in-java-virtual-machine/)

内存有两种类型:堆栈内存和堆内存。所有的动态分配进入堆内存，其余的静态分配和变量分配进入堆栈内存。每当 java 程序在 java 虚拟机中执行时，它都会使用堆内存来管理数据。任务引擎运行在 JVM (Java 虚拟机)上。层次结构如下图所示。

![](img/073fb3fee4e827b4bc7924526a171d23.png)

现在进入堆内存，堆是 Java 虚拟机(JVM)使用的内存位置。Java 虚拟机有一个在所有 Java 虚拟机线程之间共享的堆。堆是运行时数据区，所有类实例和数组的内存都是从这个数据区分配的。堆是在虚拟机启动时创建的。对象的堆存储由自动存储管理系统(称为垃圾收集器)回收；从不显式地重新分配对象。Java 虚拟机假设没有特定类型的自动存储管理系统，存储管理技术可以根据实施者的系统要求进行选择。堆可以是固定大小的，或者可以根据计算的需要进行扩展，如果不需要更大的堆，则可以收缩堆。堆的内存不需要连续。

Java 虚拟机实现可以为程序员或用户提供对堆初始大小的控制，如果堆可以动态扩展或收缩，还可以提供对最大和最小堆大小的控制。每当计算需要的堆超过自动存储管理系统所能提供的堆时，Java 虚拟机就会抛出 [OutOfMemoryError。](https://www.geeksforgeeks.org/understanding-outofmemoryerror-exception-java/)

默认情况下，JVM 堆大小为 1GB，通常足以容纳任务引擎使用的数据。但是，在某些情况下可能需要更大的堆大小，例如，当任务中参数的平均大小非常大时。在这些情况下，任务引擎日志文件中会记录以下日志项目。如果此日志项定期出现，则需要增加堆大小。

现在的问题是如何增加内存的堆大小。因此，现在可以使用命令行选项来改变/增加 JVM 堆的大小，这是一个常见的解决方案。

```java
-Xms : To set an initial java heap size
-Xmx : To set maximum java heap size
-Xss : To set the Java thread stack size
-Xmn : For setting the size of young generation, rest of the space goes for old generation
```

**过程:**增加应用服务器 JVM 堆大小

1.  登录到应用服务器管理服务器。
2.  导航到 JVM 选项。
3.  编辑-Xmx256m 选项。
4.  此选项设置 JVM 堆大小。
5.  将-Xmx256m 选项设置为更高的值，例如 Xmx1024m。
6.  保存新设置。

> **注:**
> 
> 更改网络服务器堆大小的过程与您只需登录网络服务器管理服务器的过程相同。之后的过程也是一样。对于大型生产项目来说，将最小-Xms 和最大-Xmx 堆大小设置为相同的值是很好的做法。为了有效地进行垃圾收集，-Xmn 值应该低于-Xmx 值。堆大小并不决定进程使用的内存量。