# Java 内存泄漏

> 原文:[https://www.geeksforgeeks.org/memory-leaks-java/](https://www.geeksforgeeks.org/memory-leaks-java/)

在 C 语言中，程序员完全控制动态创建对象的分配和解除分配。如果程序员不销毁对象，[内存泄漏发生在 C](https://www.geeksforgeeks.org/what-is-memory-leak-how-can-we-avoid/) ，

Java 进行自动垃圾收集。然而，可能存在垃圾收集器不收集对象的情况，因为存在对它们的引用。可能会出现应用程序创建大量对象而不使用它们的情况。仅仅因为每个对象都有有效的引用，Java 中的[垃圾收集器](https://www.geeksforgeeks.org/garbage-collection-java/)就不能破坏对象。这种类型的无用对象被称为内存泄漏。如果分配的内存超出限制，程序将因内存溢出而终止。因此，如果不再需要某个对象，强烈建议使该对象适合垃圾收集器。否则，我们应该使用一些进行内存管理的工具来识别无用的对象或内存泄漏，如:

*   [HP OVO]
*   【惠普 J METER】
*   jprobe(jprobe)
*   IBM Tivoli

## Java

```
// Java Program to illustrate memory leaks
import java.util.Vector;
public class MemoryLeaksDemo
{
    public static void main(String[] args)
    {
        Vector v = new Vector(214444);
        Vector v1 = new Vector(214744444);
        Vector v2 = new Vector(214444);
        System.out.println("Memory Leaks");
    }
}
```

输出:

```
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space exceed
```