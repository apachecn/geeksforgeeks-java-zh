# 如何在 Java 中找到最大内存、空闲内存和总内存？

> 原文:[https://www . geesforgeks . org/find-max-memory-free-memory-total-memory-Java/](https://www.geeksforgeeks.org/find-max-memory-free-memory-total-memory-java/)

虽然 Java 提供了自动[垃圾收集](https://www.geeksforgeeks.org/garbage-collection-java/)，但有时候你会想知道对象堆有多大，还剩下多少。这些信息可以用来检查代码的效率，并检查大约还有多少特定类型的对象可以被实例化。为了获得这些值，我们使用
**totalMemory()** 和 **freeMemory** 方法。

正如我们所知，Java 的垃圾收集器定期运行以回收未使用的对象。我们可以通过调用 **gc()** 方法按需调用垃圾收集器。一个值得尝试的好方法是先调用 **gc()** ，然后调用 **freeMemory()** 。

**方法:**

*   **void gc():** 运行垃圾收集器。调用此方法建议 Java 虚拟机将精力扩展到回收未使用的对象，以便使它们当前占用的内存可用于快速重用。当控制从方法调用返回时，虚拟机已经尽最大努力回收所有丢弃的对象。
    **语法:**

```
public void gc()
Returns: NA.
Exception: NA.
```

*   **long freeMemory():** 此方法返回 Java 虚拟机中的空闲内存量。调用 gc 方法可能会导致 freeMemory 返回的值增加。
    **语法:**

```
public long freeMemory()
Returns: an approximation to the total
amount of memory currently available for
future allocated objects, measured in bytes.
Exception: NA.
```

*   **long totalMemory():** 此方法返回 Java 虚拟机中的内存总量。此方法返回的值可能会随着时间的推移而变化，具体取决于主机环境。
    **语法:**

```
public long totalMemory()
Returns: the total amount of memory 
currently available for current and future 
objects, measured in bytes.
Exception: NA.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code illustrating gc(), freeMemory()
// and totalMemory() methods
class memoryDemo
{
    public static void main(String arg[])
    {
        Runtime gfg = Runtime.getRuntime();
        long memory1, memory2;
        Integer integer[] = new Integer[1000];

        // checking the total memory
        System.out.println("Total memory is: "
                           + gfg.totalMemory());

        // checking free memory
        memory1 = gfg.freeMemory();
        System.out.println("Initial free memory: "
                                      + memory1);

        // calling the garbage collector on demand
        gfg.gc();

        memory1 = gfg.freeMemory();

        System.out.println("Free memory after garbage "
                           + "collection: " + memory1);

        // allocating integers
        for (int i = 0; i < 1000; i++)
            integer[i] = new Integer(i);

        memory2 = gfg.freeMemory();
        System.out.println("Free memory after allocation: "
                           + memory2);

        System.out.println("Memory used by allocation: " +
                                    (memory1 - memory2));

        // discard integers
        for (int i = 0; i < 1000; i++)
            integer[i] = null;

        gfg.gc();

        memory2 = gfg.freeMemory();
        System.out.println("Free memory after  "
            + "collecting discarded Integers: " + memory2);
    }
}
```

输出:

```
Total memory is: 128974848
Initial free memory: 126929976
Free memory after garbage collection: 128632384
Free memory after allocation: 127950744
Memory used by allocation: 681640
Free memory after collecting discarded Integers: 128643696
```

本文由**阿比舍克·维尔马(特立独行)**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。