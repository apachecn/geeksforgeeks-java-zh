# 如何提高 Java 应用的性能？

> 原文:[https://www . geesforgeks . org/如何提高 java 应用程序的性能/](https://www.geeksforgeeks.org/how-to-improve-the-performance-of-java-applications/)

最初，Java 比 c 慢近 100 倍。后来，在开始使用 JVM 后，性能得到了提高。Java 是一种解释语言，因此它生成中间字节代码。 [**Java**](https://www.geeksforgeeks.org/java/) 用户友好，用户界面与平台无关。Java 支持面向对象编程，通过它我们可以实现真实世界的例子。Java 有一个内置的多线程工具，这对任何程序的整体执行都非常有帮助。Java 支持分布式编程，因此受到大多数开发人员的喜爱。它还具有自动垃圾收集功能。Java 省略了 C++的一个叫做指针的特性。Java 是可移植的。Java 虚拟机(JVM)是 Java 性能背后的主要支柱。

### **判断 Java 应用程序性能的依据:**

**1。商业交易:**商业交易是最能反映用户体验的衡量标准，因此是判断应用性能的重要因素。如果存储空间没有弹性，那么业务交易首先会受到影响。

**2。外部依赖:**外部依赖会以意想不到的方式显著影响 Java 应用程序。它可以有各种形式，如网络服务、小程序、数据库，以及我们的 Java 应用程序通过它们进行交互。我们可以控制外部依赖项的配置，所以当特定的依赖项无法工作时，知道问题是很重要的，我们应该想出一个安全机制来克服这个问题。

**3。缓存策略:**从内存中提取数据总是比进行网络调用提取数据更快(例如:从数据库服务器中检索数据)。缓存提供了一种在本地存储对象实例的机制，可以更快地访问数据。在决定高速缓存策略时，需要考虑的重要事情是适当地调整高速缓存的大小，并且应该确保不会有太多的数据加载到高速缓存中。

**4。垃圾收集:**Java 中的垃圾收集对用户非常有帮助，因为它自动释放内存，而不是手动管理(像 C、C++这样的语言)。然而，垃圾收集是好事也是坏事。当我们使用完一个对象时，我们只需删除对该对象的引用，垃圾收集会自动为我们释放它。当没有对内存的引用时，垃圾收集器会自动释放内存。但是，当分配内存时，在内存释放之前，对该内存的引用会被删除。调整堆大小和垃圾收集策略以满足应用程序行为非常重要。

**5。应用拓扑:**判断 Java 应用性能的最终性能组件是应用拓扑。由于云的到来，应用环境正在根据用户需求进行高低调整。业务事务负载和容器性能是我们构建应用程序拓扑时要考虑的两个重要指标。分析每个应用程序组件的性能并相应地调整拓扑非常重要。

### **提高 Java 应用程序性能的方法**

*   **谨慎使用正则表达式:**正则表达式相对便宜方便。如果在计算密集型代码段中使用正则表达式，我们至少应该将引用模式存储在缓存中。
*   **尽可能避免递归:**递归在很多情况下都会带来麻烦。所以我们应该尽量减少递归的使用，或者想出一些机制来识别递归带来的麻烦。
*   **性能测试套件:**该测试运行将有助于识别应用程序的功能和性能副作用。如果应用程序有太多的外部依赖项，比如数据库或缓存，那么这个测试就很重要。
*   **使用 StringBuilder 进行字符串连接:**使用 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 代替字符串在性能上非常有用。如果你正在做大量的字符串操作，正常的字符串会减少内存，因为它会产生大量的垃圾。
*   **使用堆栈并避免堆:**提高应用程序的性能是使用基元类型而不是它们的包装类。建议将该值存储在堆栈中，而不是堆中，以减少内存消耗并更有效地处理它。
*   **并发控制:**同时运行多个程序会导致性能下降。正确使用数据访问框架将提高数据访问层的性能，这种策略可以为整个应用程序带来优化收益。
*   **缓存:**重用资源更有效，有助于提高应用程序的性能。缓存是提高响应能力的好方法，您可以使用它来优化您的 Java 应用程序性能。
*   **枚举:**也可以称为[枚举](https://www.geeksforgeeks.org/enummap-class-java-example/)。在这个实现中，我们有一个索引值数组，而不是哈希表。如果数值比较少的话，确实应该考虑使用[枚举](https://www.geeksforgeeks.org/enumset-class-java/)或者枚举映射，而不是常规的 HashSet 或者 HashMap。
*   **线程处理:**避免创建和销毁过多线程。创建和处理线程是 JVM 性能问题的常见原因，因为创建和销毁线程对象相对较重。
*   **JDBC 性能:**关系数据库也是 Java 应用程序性能的另一个原因。 [JDBC](https://www.geeksforgeeks.org/jdbc-drivers/) 批处理有助于有效地处理数据库。