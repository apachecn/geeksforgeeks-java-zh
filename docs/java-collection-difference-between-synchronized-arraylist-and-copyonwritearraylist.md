# Java 集合|同步数组列表和 CopyOnWriteArrayList 的区别

> 原文:[https://www . geesforgeks . org/Java-collection-difference-synchronized-ArrayList-and-copy onwriterarraylist/](https://www.geeksforgeeks.org/java-collection-difference-between-synchronized-arraylist-and-copyonwritearraylist/)

由于**数组列表**不同步，如果多个线程试图同时修改一个数组列表，那么最终的结果将是不确定的。因此，为了在多线程环境中实现线程安全，必须同步数组列表。

数组列表的同步可以通过两种方式完成:

1.  **使用收藏品。同步列表()**
2.  **使用 copy onwriterrarray list(COWAL).**

由于两者都用于实现 Arraylist 中的线程安全，因此出现了一个问题，即何时使用 COWAL 以及何时使用 Collection.synchronizedList()。这可以通过理解它们之间的差异来理解。同步数组列表和 CopyOnWriteArrayList 之间的主要区别来自于它们的性能、可伸缩性以及它们如何实现线程安全。

### 为什么当 Collection.synchronizedList()已经存在时，CopyOnWriteArrayList 才出现

最初，SynchronizedList 用于多线程环境，但它有一些限制。它的所有读写方法都是在列表对象本身上同步的，也就是说，如果一个线程正在执行 add()方法，它会阻止其他想要让迭代器访问列表中元素的线程。此外，一次只允许一个线程迭代列表元素，这是低效的。那是相当僵硬的。

因此，需要一个更灵活的集合，它允许:

1.  Multiple threads simultaneously perform read operations.
2.  One thread concurrently performs read operation and the other thread concurrently performs write operation.
3.  Only one thread can write, and other threads can read at the same time.

为了克服这些问题，最终在 **Java 5** 中，引入了一组名为**并发集合**的新集合类，其中包含**copy onwriterarraylist**。CopyOnWriteArrayList 类旨在启用这种顺序写入和并发读取功能。

### 它们之间的主要区别是:

1.  **Locking of threads :** **Synchronized List** locks the whole list to provide synchronization and thread-safety during the read or write operation, while, **CopyOnWriteArrayList** doesn’t lock the whole list during these operations.

    CopyOnWriteArrayList 类根据其名称工作，即*写时复制*，它对读写操作执行不同的操作。对于每个写操作(添加、设置、删除等)，它都会生成列表中元素的新副本。对于读取操作(get、迭代器、listIterator 等)，它在不同的副本上工作。因此在读操作期间没有额外的开销，并且它的读操作比 Collections 更快。SynchronizedList()。因此， **COWAL 比同步列表更适合读取操作。**

2.  **Write operation:** For the write operation in array list, **Cowal write operation is slower than Collections.synchronizedList (),** because it uses Re-entrantLock. The write method will always create a copy of the existing array, modify the copy, and finally update the volatile reference of the array to point to this new array. Therefore, it has a lot of overhead during the write operation. That's why the CopyOnWriteArrayList write operation is slower than the Collections.synchronizedList ().
3.  **Behavior when modifying:** **Synchronized list is a fast iterator for failure** , that is, when a thread modifies the list while iterating over it, it will throw a concurrent verification exception. And **copyonwriterraylist is a fail-safe iterator** , that is, when a thread modifies the list while iterating over it, it will not throw a concurrency verification exception.
4.  **Number of worker threads:** By locking the complete list objects that affect its performance, only one thread is allowed to operate on the synchronized list because other threads are waiting, while in the case of **Cowal** , multiple threads are allowed to operate on the array list because it works on a separate clone copy, which is used for updating/modifying operation **to make its performance faster**
5.  **Iteration within the block:** When iterating the synchronization list, ensure that it is iterated within the synchronization block, while in CopyOnWriteArrayList, we can safely iterate outside the synchronization block.

    ### When to use the SynchronizedList?

    1.  Because in CopyOnWriteArrayList, for every update/modification operation, a new independent clone copy will be created, and there is an overhead of memory allocation on JVM & merging the clone copy with the original copy. Therefore, in this case, the synchronization list is a better choice.
    2.  数组列表大的时候

        ### 什么时候使用 CopyOnWriteArrayList？

        ### 同步列表 v/s 副本 on writerrarray list

        | 同步列表 | copy writer Arraylist |
        | --- | --- |
        | 它在读或写操作期间锁定整个列表，以确保线程安全。 | 只在写操作时锁定列表，所以在读操作时不锁定。因此，多个线程同时执行读取操作。 |
        | 它是一个快速失败迭代器。 | 它是一个故障安全迭代器。 |
        | 它是在 Java 版本中引入的。 | 是在 Java 版本中引入的。 |
        | 列表的迭代应该在同步块内部，否则会面临不确定行为。 | 它可以安全地在同步块外迭代。 |
        | 当一个线程遍历列表时，如果有其他线程试图修改列表，它将抛出 Concurrentmodification Exception。 | 遍历时不允许修改列表。如果列表在遍历过程中被其他线程修改，则不会引发并发验证异常。 |
        | 最好在数组列表较大且列表中的写操作大于读操作时使用。 | 最好在 ArrayList 小或者读操作大于写操作时使用。 |

        1.  Copywriter Arraylist provides lock-free reading, which means that if there are more reading threads, and writing happens quite slowly, the performance will be much better.
        2.  When the size of the array list is small.