# 常见 Java 编程面试问题|第 1 集

> 原文:[https://www . geesforgeks . org/common-question-Java-programming-interview-questions-set-1/](https://www.geeksforgeeks.org/commonly-asked-java-programming-interview-questions-set-1/)

**Java 为什么被称为‘平台无关编程语言’？**T3】

平台无关性意味着程序的执行不依赖于操作系统的类型(可以是任何类型:Linux、windows、Mac..等等)。所以只编译一次代码，并在任何系统上运行它(在 C/C++中，我们需要为运行它的每台机器编译代码)。Java 是基于编译器(javac)和解释器(jvm)的语言。您的 java 源代码首先使用 javac 编译器编译成字节码。使用 JVM 可以很容易地将这个字节码转换成等价的机器代码。JVM(Java 虚拟机)在我们安装的所有操作系统中都可用。因此，javac 生成的字节代码是通用的，可以在任何操作系统上转换成机器代码，这就是 java 独立于平台的原因。

**用 java 解释 Final 关键字？**T3】

java 中的 Final 关键字用于限制变量、类和方法的使用。

变量:Final 变量的值为常量，不能更改。
方法:你不能覆盖最终方法。
类:不能继承 Final 类。

详见[本](https://www.geeksforgeeks.org/final-keyword-java/)

**超级关键词是什么时候用的？**

超级关键词用来指代:

*   直接父类构造函数，
*   直接父类变量，
*   直接父类方法。

详见[本](https://www.geeksforgeeks.org/super-keyword/)。

**StringBuffer 和 String 有什么区别？**T3】

字符串是一个不可变的类，也就是说，一旦创建，您就不能修改它的内容。虽然 StringBuffer 是一个可变类，但这意味着您可以在以后更改它的内容。每当我们更改 String 对象的内容时，它都会创建一个新的字符串并引用它，而不会修改现有的字符串。这就是 StringBuffer 的性能优于 String 的原因。
详见[本](https://www.geeksforgeeks.org/g-fact-27-string-vs-stringbuilder-vs-stringbuffer/)。

**为什么 java 不支持多重继承？**T3】

Java 支持多重继承，但不是通过类，它只支持通过它的接口。不支持多重继承的原因是为了避免由此产生的冲突和复杂性，并保持 Java 是一种简单的面向对象语言。如果我们回忆一下[这一点，在 C++](https://www.geeksforgeeks.org/multiple-inheritance-in-c/) 中，有一个多重继承的特殊情况(菱形问题)，你有一个多重继承，有两个类有方法冲突。所以，Java 开发人员决定避免这样的冲突，根本不允许通过类进行多重继承。

**一个顶级类可以是私有的还是受保护的？**T3】

java 中的顶级类不能是私有的或受保护的，但是 java 中的内部类可以。没有将顶级类设为私有的原因非常明显，因为没有人可以看到私有类，因此他们不能使用它。将类声明为受保护的也没有任何意义。默认可见性和受保护可见性之间的唯一区别是，我们可以通过继承它在任何包中使用它。因为在 java 中没有包继承的概念，所以将类定义为受保护的和默认的没有什么不同。

**Java 异常处理中的‘抛出’和‘抛出’有什么区别？**T3】

以下是两者之间的区别:

*   throw 关键字用于从任何方法或静态块中抛出异常，而 throws 用于指示该方法可能抛出哪个异常
*   如果任何方法抛出选中的异常，那么调用者可以处理这个异常(使用 try catch 块)，或者通过在方法声明中声明另一个“抛出”子句来重新抛出它。
*   throw 子句可以用在代码中您认为需要向调用方法抛出特定异常的任何部分

例如
**抛出**
抛出新异常(“你有一些异常”)
抛出新异常(“连接失败！!")
**抛出**
抛出 IOException，NullPointerException，ArithmeticException

**什么是 finalize()方法？**

与 c++不同，我们不需要在 Java 中显式销毁对象。[垃圾收集器](https://www.geeksforgeeks.org/garbage-collection-java/)'自动为我们做。垃圾收集器检查是否不存在对某个对象的引用，该对象是否不再需要，以及该对象占用的内存是否可以释放。有时一个对象可以保存非 java 资源，如文件句柄或数据库连接，那么您需要确保这些资源在对象被销毁之前也被释放。为了执行这样的操作，Java 在对象类中提供了受保护的 void finalize()。您可以在类中重写此方法，并执行所需的任务。就在对象被释放之前，java 运行时调用该对象上的 finalize()方法。详见[本](https://www.geeksforgeeks.org/garbage-collection-java/)。

**设置和列表界面的区别？**T3】

集合和列表都是集合接口的子接口。它们之间有以下两个主要区别

*   列表可以包含重复的值，但是“设置”不允许这样做。
*   在列表界面中，数据以您插入的顺序出现，但在集合的情况下，插入顺序不会保留。

**如果将 System.exit(0)置于 try 或 catch block 上，会发生什么情况？最终会阻止执行吗？**

通过在 try 或 catch block 中调用 System.exit(0)，我们可以跳过 finally block。System.exit(int)方法可以引发 SecurityException。如果 Sysytem.exit(0)退出 JVM 而没有抛出该异常，那么 finally 块将不会执行。但是，如果 System.exit(0)确实引发了安全异常，那么将执行 finally block。

*   [常见 Java 编程面试问题|第二集](https://www.geeksforgeeks.org/commonly-asked-java-programming-interview-questions-set-2/)
*   【Java 专业人士面试问题
*   练习 Java 的[小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)
*   爪哇[文章](https://www.geeksforgeeks.org/java/)T2】

本文由**达尔梅什·辛格**整理。

您可能希望看到以下内容:

[常见 C 编程面试问题|第 1 集](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/ "Permanent link to Commonly Asked C Programming Interview Questions | Set 1")
[常见 C 编程面试问题|第 2 集](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/ "Permanent link to Commonly Asked C Programming Interview Questions | Set 2")
[亚马逊最常问的面试问题](https://www.geeksforgeeks.org/amazon-interview-questions/)
[微软最常问的面试问题](https://www.geeksforgeeks.org/microsofts-asked-interview-questions/ "Permanent link to Microsoft’s most asked interview questions")
埃森哲最常问的面试问题
[常见的面向对象面试问题](https://www.geeksforgeeks.org/commonly-asked-oop-interview-questions/ "Permanent link to Commonly Asked OOP Interview Questions | Set 1")
[常见的 C++面试问题](https://www.geeksforgeeks.org/commonly-asked-c-interview-questions-set-1/ "Permanent link to Commonly Asked C++ Interview Questions | Set 1")
T21】常见的 DBMS 面试问题| 集合 1
[常见的 DBMS 面试问题|集合 2](https://www.geeksforgeeks.org/commonly-asked-dbms-interview-questions-set-2/)
[常见的操作系统面试问题|集合 1](https://www.geeksforgeeks.org/commonly-asked-operating-systems-interview-questions-set-1/)
[常见的数据结构面试问题。](https://www.geeksforgeeks.org/commonly-asked-data-structure-interview-questions-set-1/ "Permanent link to Commonly Asked Data Structure Interview Questions | Set 1")
[常见算法面试问题](https://www.geeksforgeeks.org/commonly-asked-algorithm-interview-questions-set-1/)
[常见计算机网络面试问题](https://www.geeksforgeeks.org/commonly-asked-computer-networks-interview-questions-set-1/)
[面试问题前 10 名算法](https://www.geeksforgeeks.org/top-10-algorithms-in-interview-questions/)