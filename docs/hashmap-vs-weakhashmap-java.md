# Java 中 Hashmap vs weakashmap

> 原文:[https://www.geeksforgeeks.org/hashmap-vs-weakhashmap-java/](https://www.geeksforgeeks.org/hashmap-vs-weakhashmap-java/)

[**【hashmap】**](https://www.geeksforgeeks.org/hashmap-treemap-java/)

类是一个基于哈希的实现。在 HashMap 中，我们有一个键和值对。
即使对象在 hashmap 中被指定为 key，它也没有任何引用，并且如果它与 HashMap 相关联，即 HashMap 优先于垃圾收集器，则它是**而不是**有资格进行垃圾收集。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// Hashmap
import java.util.*;
class HashMapDemo
{
    public static void main(String args[])throws Exception
    {
        HashMap m = new HashMap();
        Demo d = new Demo();

        // puts an entry into HashMap
        m.put(d," Hi ");

        System.out.println(m);
        d = null;

        // garbage collector is called
        System.gc();

        //thread sleeps for 4 sec
        Thread.sleep(4000);

        System.out.println(m);
        }
    }
    class Demo
    {
        public String toString()
        {
            return "demo";
        }

        // finalize method
        public void finalize()
        {
            System.out.println("Finalize method is called");
        }
}
```

输出:

```
{demo=Hi}
{demo=Hi}
```

**天气图**

WeakHashMap 是地图界面的一个实现。weakashmap 与 HashMap 几乎相同，除了 weakashmap 的情况，如果对象被指定为键不包含任何引用-即使它与 weakashmap 相关联，它也有资格进行垃圾收集。也就是说，垃圾收集器在地图上占据主导地位。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// WeakHashmap
import java.util.*;
class WeakHashMapDemo
{
    public static void main(String args[])throws Exception
    {
        WeakHashMap m = new WeakHashMap();
        Demo d = new Demo();

        // puts an entry into WeakHashMap
        m.put(d," Hi ");
        System.out.println(m);

        d = null;

        // garbage collector is called
        System.gc();

        // thread sleeps for 4 sec
        Thread.sleep(4000); .

        System.out.println(m);
    }
}

class Demo
{
    public String toString()
    {
        return "demo";
    }

    // finalize method
    public void finalize()
    {
        System.out.println("finalize method is called");
    }
}
```

输出:

```
{demo = Hi}
finalize method is called
{ }
```

【Hashmap 和 WeakHashmap 的一些更重要的区别:

1.  [**【强参照 vs 弱参照】**](https://www.geeksforgeeks.org/types-references-java/) :弱参照对象不是参照对象的默认类型/类别，使用时应明确指定。这种类型的引用在 WeakHashMap 中用于引用条目对象。
    强引用:这是引用对象的默认类型/类。任何具有活动强引用的对象都不适合垃圾收集。在 HashMap 中，关键对象具有强引用。
2.  **垃圾收集器的作用:**垃圾收集:在 Hashmap 中，条目对象(条目对象存储键值对)没有资格进行垃圾收集，即 HashMap 优于垃圾收集器。
    在 WeakHashmap 中，当一个键被丢弃时，它的条目会自动从地图中移除，换句话说，就是垃圾回收。
3.  [**克隆方法**](https://www.geeksforgeeks.org/clone-method-in-java-2/) **实现:** HashMap 实现可克隆接口。
    weakashmap 不实现可克隆接口，只实现 Map 接口。因此，在 WeakHashMap 类中没有 clone()方法。

本文由**里沙布·帕特尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。