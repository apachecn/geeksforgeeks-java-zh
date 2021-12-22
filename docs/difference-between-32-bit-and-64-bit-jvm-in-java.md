# Java 中 32 位和 64 位 JVM 的区别

> 原文:[https://www . geesforgeks . org/32 位和 64 位 Java JVM 的区别/](https://www.geeksforgeeks.org/difference-between-32-bit-and-64-bit-jvm-in-java/)

除非开发性能关键的应用程序，否则不需要知道区别。32 位和 64 位 JVM 之间的细微差别在您的应用程序中没有什么区别。

现在来看差异，我们将列出 32 位和 64 位 [Java 虚拟机](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/)之间的一些关键差异，下面列出了这些差异，我们根据让步因素对它们进行了比较，让步因素如下:

1.  In 64-bit JVM, you can specify more memory for heap size than 32-bit JVM; For example, in a 32-bit JVM, the theoretical maximum memory limit is 4GB, while 64 bits are much higher.
2.  The 64-bit JVM is especially useful for Java applications with a large heap, such as those that use more than 100 GB of memory at most.
3.  Because the size of OOP (ordinary object pointer) has increased from 32 bits to 64 bits, the same Java application will use more memory in 64-bit JVM than 32-bit JVM. If you use JVM option -xxcpressedoop, you can get rid of it, which tells JVM to use 32-bit pointer.
4.  The next significant change we see is that in the 64-bit JVM architecture, the object header size is now 12 bytes, instead of 8 bytes in the 32-bit JVM. Another change is the size of internal reference, which can now reach 8 bytes, while 32-bit JVM can only reach 4 bytes.
5.  There are separate installers for 32-bit and 64-bit JVMs.
6.  Client JVM is only suitable for 32-bit JVM, not 64-bit JVM.

如上所述，我们已经看到了这样的差异，但是请记住一个关于 64 位 JVM 性能如何比 32 位 JVM 慢的注释？

这是因为系统中的每个本机指针占用八个字节，而不是四个字节。加载这些额外的数据会增加内存使用量，这将导致执行速度稍慢，具体取决于 Java 程序执行期间加载了多少指针。Java 虚拟机获得了一些额外的寄存器，可以用来创建更高效的本机指令序列。当比较 32 位和 64 位执行速度时，这些额外的寄存器将性能提高到通常完全没有性能损失的程度。

从 32 位 JVM 迁移到 64 位 JVM 时需要考虑的几点如下:

*   Garbage collector pause time
*   Primary reservoir

**因子 1:** 气相色谱暂停时间

从 32 位 JVM 切换到 64 位 JVM 的主要动机是增加堆大小(即-Xmx)。当您增加堆大小时，您的垃圾收集暂停时间将自动增加，因为内存中没有更多垃圾需要清除。在执行迁移之前，您必须执行适当的 GC 调优；否则，您的应用程序可能会经历几秒到几分钟的暂停。为了给新增加的堆大小提供正确的垃圾收集设置，您可以使用像 GCeasy 这样的工具。

**因子 2:** 原生文库

如果您的应用程序通过 Java 本机接口(JNI)访问本机库，您还需要升级本机库，因为 32 位 JVM 只能使用 32 位本机库。同样，64 位 JVM 只能使用 64 位的本机库。

> **注意:**什么时候该用 32 位还是 64 位的 Java 虚拟机？
> 
> *   If your application's heap size (i.e. -Xmx) is less than 2GB, this is easy. Use 32-bit JVM. ( **< 2GB memory** )
> *   If your application needs more than 2GB of memory, you don't need to think. Be sure to use 64-bit JVM ( **> 2GB memory** )