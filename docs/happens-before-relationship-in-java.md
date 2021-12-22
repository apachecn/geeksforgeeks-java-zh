# 发生 Java 中的关系之前

> 原文:[https://www . geeksforgeeks . org/pref-before-relationship-in-Java/](https://www.geeksforgeeks.org/happens-before-relationship-in-java/)

**先决条件:** [穿线](https://www.geeksforgeeks.org/multithreading-in-java/)[同步闭塞](https://www.geeksforgeeks.org/synchronized-in-java/)[易失关键字](https://www.geeksforgeeks.org/volatile-keyword-in-java/)

“发生在前”是一个概念、一种现象，或者仅仅是定义编译器或中央处理器对指令重新排序的基础的一组规则。在 Java 语言中，before 不是任何关键字或对象，它只是一个规则，在多线程环境中，对周围指令的重新排序不会导致代码产生不正确的输出。

如果这是你第一次遇到这个概念，这个定义可能看起来有点难以接受。要理解它，让我们首先了解对它的需求从何而来。

Java 内存模型也称为 JMM 模型，它定义了在单个或多线程环境中，线程和硬件之间如何存储和交换数据。

需要牢记的几点如下:

*   每个 CPU 内核都有自己的一组寄存器。
*   每个 CPU 内核一次可以执行多个线程。
*   每个 CPU 内核都有自己的一组缓存。
*   一个线程在一个中央处理器内核上执行，但是它的数据是从内存中存储和访问的，内存中的局部变量位于“线程堆栈”中，而对象位于“堆”中

![](img/649848f29372e541053f467fed5f1d03.png)

Java 内存模型

线程内部的局部变量和对象引用存储在线程堆栈中，而对象本身存储在堆中。运行在中央处理器上的线程对变量的请求遵循以下路线*内存- >缓存- >中央处理器寄存器。*类似地，当变量发生一些处理并且其值被更新时，这些变化通过*中央处理器寄存器- >高速缓存- >随机存取存储器。*因此，当使用共享一个变量的多个线程时，当一个线程更新一个共享变量的值时，必须先更新寄存器，然后更新缓存，最后更新内存。当另一个线程需要读取共享变量时，它会读取内存中的值，该值会通过缓存和寄存器传输。如果从基本层面来看，如果读写操作被延迟，使得在执行另一次读写之前，正确的值没有存储在内存中，那么它可能会导致内存一致性错误。

当使用多个线程时，这种存储和检索过程可能会带来一些问题，例如:

*   [**竞态条件**](https://www.geeksforgeeks.org/introduction-of-process-synchronization/) :两个线程共享某个变量，对其进行读写，但不同步，导致值不一致的情况。
*   **更新可见性**:其中一个线程对共享变量的更新可能对另一个线程不可见，因为该值尚未更新到内存中。

这些问题通过使用同步块和可变变量来解决。

**指令重新排序**

在编译或处理过程中，编译器或中央处理器可能会对指令重新排序以并行运行它们，从而提高吞吐量和性能。例如，我们有 3 个指令:

```java
FullName = FirstName + LastName        // Statement 1
UniqueId = FullName + TokenNo         // Statement 2

Age = CurrentYear - BirthYear        // Statement 3
```

编译器不能并行运行 1 和 2，因为 2 需要 1 的输出，但是 1 和 3 可以并行运行，因为它们彼此独立。因此，编译器或中央处理器可以这样重新排序这些指令:

```java
FullName = FirstName + LastName      // Statement 1
Age = CurrentYear - BirthYear       // Statement 3

UniqueId = FullName + TokenNo        // Statement 2
```

然而，如果在多线程应用程序中执行重新排序，其中线程共享一些变量，那么它可能会让我们失去程序的正确性。

现在回想一下我们在前一节中谈到的两个问题，比赛状态和更新的可见性。Java 为我们提供了一些解决方案来处理这些类型的情况。我们将了解它们是什么，最后会发生什么-之前将在这一部分介绍。

**挥发性**

对于声明为易失性的字段/变量，

```java
private volatile count;
```

*   对该字段的每次写入都将被直接写入/刷新到主存储器(即绕过高速缓存)。)
*   该字段的每次读取都是直接从主存储器中读取的。

这意味着共享变量*计数，*无论何时被线程写入或读取，它总是对应于其最近写入的值。这将防止竞争条件，因为现在线程将总是使用共享变量的正确值。此外，对共享变量的更新也将对所有读取它的线程可见，从而防止了更新可见性问题。

波动性决定了一些更重要的观点:

*   在写入易失性变量时，该线程可见的所有非易失性变量也将被写入/刷新到主内存，即它们的最新值将与易失性变量一起存储在内存中。
*   在您读取易失性变量时，该线程可见的所有非易失性变量也将从主内存中刷新，即它们的最新值将被分配给它们。

这被称为的**可见度保证，一个**可变变量**。**

所有这些看起来和工作正常，除非中央处理器决定重新排序您的指令，导致您的应用程序执行不正确。让我们理解我们的意思。考虑程序的这一部分:

**实施:**

下图中的代码用简单的语言描述如下:

*   输入学生提交的新作业
*   然后收集新任务。

我们的目标是每次“只收集新准备的作业。因此建议如下所示的示例代码:

插图:

```java
// Sample class
class ClassRoom {

    // Declaring and initializing variables
    // of this class
    private int numOfAssgnSubmitted = 0;
    private int numOfAssgnCollected = 0;
    private Assignment assgn = null;
    // Volatile shared variable
    private volatile boolean newAssignment = false;

    // Methods of this class

    // Method 1
    // Used by Thread 1
    public void submitAssignment(Assignment assgn)
    {

        // This keyword refers to current instance itself
        // 1
        this.assgn = assgn;
        // 2
        this.numOfAssgnSubmitted++;
        // 3
        this.newAssignment = true;
    }

    // Method 2
    // Used by Thread 2
    public Assignment collectAssignment()
    {
        while (!newAssignment) {

            // Wait until a new assignment is submitted
        }

        Assignment collectedAssgn = this.assgn;

        this.numOfAssgnCollected++;
        this.newAssignment = true;

        return collectedAssgn;
    }
}
```

*   线程 Thread1 使用 **submitAssignment()** 方法，线程 thread 1 在 assign 字段接受学生提交的作业，然后增加提交的作业数，然后将 newAssignment 变量翻转为 true。
*   线程 Thread2 使用方法 **collectAssignment()** ，线程 thread 2 等待直到提交新的赋值，当 newAssignment 的值变为 true 时，它将提交的赋值存储到变量*‘collectedasssgn’，*中，增加收集的赋值计数并将 new assignment 翻转为 false，因为没有剩余的未决赋值。最后，它返回收集的赋值。

现在，易失性变量 **newAssignment** 充当并发运行的线程 1 和线程 2 之间的共享变量。由于所有其他变量对每个线程和 newAssignment 本身都是可见的，读写操作将直接使用主内存完成。

如果我们关注 submitAssignment()方法，语句 1、2 和 3 是相互独立的，因为没有语句使用另一个语句，因此您的 CPU 可能会想“为什么不重新排序它们？”无论出于什么原因，它都可以提供更好的性能。因此，让我们假设 CPU 以这种方式重新排序了三个语句:

```java
this.newAssignment = true; // 3
this.assgn = assgn;   // 1
this.numOfAssgnSubmitted++; // 2
```

现在想一想，我们的目标是什么，它是每次收集一个新的新赋值，但是现在由于语句 3 甚至在新的 assgn 已经存储在 assgn 中之前就将 new assgn 更新为 true，线程 2 中的 while 循环现在将退出，并且有可能线程 2 的指令在线程 1 的剩余指令之前执行，导致提交赋值的旧值对象。即使这些值是直接从主存储器中检索的，如果在这种情况下指令以错误的顺序执行也是没有用的。

在这一点上，即使保证了变量的可见性，指令的重新排序也可能导致不正确的执行。因此，关于易变变量的可见性，Java 引入了先发生后保证。

**发生在-挥发**之前

发生在关于重新排序的状态之前。具体如下:

*   当重新排序在写入易失性变量之前发生的对变量的任何写入时，将保留在写入易失性变量之前。
*   当对位于某个非易失性或易失性变量读取之前的易失性变量的任何读取进行重新排序时，保证会在任何后续读取之前发生。

就上述例子而言，第一点是相关的。在写入易失性变量(语句 3)之前发生的对变量(语句 1 和 2)的任何写入都将保留在对易失性变量的写入之前。这意味着禁止在 1 和 2 之前对语句 3 进行重新排序。这反过来保证了只有在赋值的新值被赋值给'*assign '*时，newAssignment 才被设置为 true。这就是所谓的**先发制人的**能见度保证。另外，语句 1 和 2 可以在它们之间重新排序，只要它们没有在语句 3 之后被重新排序。

**同步块**

在 Java 同步块的情况下:

*   当一个线程进入同步块时，该线程将从主内存中刷新该线程当时可见的所有变量的值。
*   当线程退出同步块时，所有这些变量的值将被写入主内存。

**在同步块中发生-之前**

在同步块的情况下，发生在用于重新排序的状态之前:

*   在同步块退出之前发生的对变量的任何写入都保证保持在同步块退出之前。
*   在读取变量之前发生的同步块的入口，保证保持在同步块入口之后的任何变量读取之前。

现在深入到 java 中发生之前关系的根源。让我们考虑一个场景来更好地理解它。

插图:

如果一个动作“x”在另一个动作“y”之前可见且有序，则由 *hb(x，y)指示的两个动作之间存在先发生关系。*

*   如果 x 和 y 是同一个线程的动作，并且在程序顺序中 x 在 y 之前，那么 hb(x，y)。
*   从对象的构造函数的末尾到该对象的终结器的开头有一个发生在前面的边。
*   如果一个动作 x 与后面的动作 y 同步，那么我们也有 hb(x，y)。
*   如果 hb(x，y)和 hb(y，z)，那么 hb(x，z)。

> **注意:**重要的是要知道，如果我们有 hb(x，y)，那么不一定意味着 x 总是出现在 y 之前的实现中，只要执行产生正确的结果，对这样的动作重新排序是合法的。

下面是关于同步状态的更多规则:

*   [监视器上的解锁发生在该监视器上的每次后续锁定之前。](https://en.wikipedia.org/wiki/Monitor_(synchronization))
*   对易失性字段的写入发生在该字段的每次后续读取之前。
*   在线程上调用 start()发生在已启动线程中的任何操作之前。
*   线程中的所有操作都发生在任何其他线程从该线程上的 join()成功返回之前。
*   任何对象的默认初始化都发生在程序的任何其他操作(默认写入除外)之前。
*   当一条语句调用 Thread.start 时，与该语句有先发生关系的每条语句也与新线程执行的每条语句有先发生关系。导致创建新线程的代码的效果对新线程是可见的。
*   当一个线程终止并导致另一个线程中的 Thread.join 返回时，被终止的线程执行的所有语句都与成功连接后的所有语句具有先发生后发生的关系。执行连接的线程现在可以看到线程中代码的效果。