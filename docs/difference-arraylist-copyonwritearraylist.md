# 数组列表和 CopyOnWriteArrayList 的区别

> 原文:[https://www . geeksforgeeks . org/difference-ArrayList-copy onwriterarraylist/](https://www.geeksforgeeks.org/difference-arraylist-copyonwritearraylist/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)和[副本写数组](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)都实现列表界面。但是数组列表和 CopyOnWriteArrayList 有很多不同之处:

*   CopyOnWriteArrayList 创建底层数组列表的克隆副本，对于特定点的每个更新操作，两者都将自动同步，这由 JVM 负责。因此，对正在执行读取操作的线程没有影响。因此，线程安全不在数组列表中，而 CopyOnWriteArrayList 是线程安全的。
*   当一个线程迭代数组列表对象时，如果另一个线程试图进行修改，那么我们将得到运行时异常，即 ConcurrentModificationException。在拷贝写数组列表的情况下，我们不会得到任何异常。
*   ArrayList 是在 JDK 1.2 中引入的，而 CopyOnWriteArrayList 是在 JDK 1.5 中由 SUN 人员引入的。
*   Iterator of ArrayList can perform remove operation while iteration. But Iterator of CopyOnWriteArrayList cant perform remove operation while iteration, otherwise it will throw run-time exception UnsupportedOperationException.

    下面是这一点的实现。

```java
// Java program to illustrate ArrayList
import java.util.*;

class CopyDemo
{
    public static void main(String[] args) 
    {
        ArrayList l = new ArrayList();
        l.add("A");
        l.add("B");
        l.add("C");
        Iterator itr = l.iterator();

        while (itr.hasNext()) 
        {
            String s = (String)itr.next();

            if (s.equals("B"))
            {
                // Can remove
                itr.remove();
            }
        }
        System.out.println(l);
    }
}
```

输出:

```java
[A,C]

```

```java
// Java program to illustrate CopyOnWriteArrayList
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

class CopyDemo extends Thread {

    static CopyOnWriteArrayList l = new CopyOnWriteArrayList();

    public static void main(String[] args) 
                throws InterruptedException
    {
        l.add("A");
        l.add("B");
        l.add("C");
        Iterator itr = l.iterator();

        while (itr.hasNext())
        {
            String s = (String)itr.next();
            System.out.println(s);

            if (s.equals("B"))
            {
                // Throws RuntimeException
                itr.remove();
            }
            Thread.sleep(1000);
        }
        System.out.println(l);
    }
}
```

输出:

```java
A
B
Exception in thread "main" java.lang.UnsupportedOperationException

```