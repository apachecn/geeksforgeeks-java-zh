# Java 中 HashMap 和 HashTable 的区别

> 原文:[https://www . geesforgeks . org/Java 中-hashmap-和-hashtable-的区别/](https://www.geeksforgeeks.org/differences-between-hashmap-and-hashtable-in-java/)

[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)和[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)将键和值对存储在哈希表中。当使用哈希表或哈希表时，我们指定一个用作键的对象以及要链接到该键的值。然后对该键进行哈希运算，得到的哈希代码用作该值在表中存储的索引。现在让我们借助一个例子来讨论一下。

**哈希表 vs 哈希表**

*   HashMap 是非同步的。它不是线程安全的，如果没有适当的同步代码，就不能在许多线程之间共享，而哈希表是同步的。它是线程安全的，可以与许多线程共享。
*   HashMap 允许一个空键和多个空值，而 Hashtable 不允许任何空键或空值。
*   如果不需要线程同步
    ，HashMap 通常比 HashTable 更受欢迎

> 极客现在**你一定很好奇为什么 HashTable 不允许 null，HashMap 做**？
> 答案**答案**很简单为了成功地从哈希表中存储和检索对象，用作键的对象必须实现 hashCode 方法和 equals 方法。因为 null 不是对象，所以它不能实现这些方法。HashMap 是 Hashtable 的高级版本和改进。HashMap 是后来创建的。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A sample Java program to demonstrate
// HashMap and HashTable
import java.util.*;
import java.lang.*;
import java.io.*;

// Name of the class has to be "Main"
// only if the class is public
class Ideone
{
    public static void main(String args[])
    {
        //----------hashtable -------------------------
        Hashtable<Integer,String> ht=new Hashtable<Integer,String>();
        ht.put(101," ajay");
        ht.put(101,"Vijay");
        ht.put(102,"Ravi");
        ht.put(103,"Rahul");
        System.out.println("-------------Hash table--------------");
        for (Map.Entry m:ht.entrySet()) {
            System.out.println(m.getKey()+" "+m.getValue());
        }

        //----------------hashmap--------------------------------
        HashMap<Integer,String> hm=new HashMap<Integer,String>();
        hm.put(100,"Amit");
        hm.put(104,"Amit"); 
        hm.put(101,"Vijay");
        hm.put(102,"Rahul");
        System.out.println("-----------Hash map-----------");
        for (Map.Entry m:hm.entrySet()) {
            System.out.println(m.getKey()+" "+m.getValue());
        }
    }
}
```

**Output**

```java
-------------Hash table--------------
103 Rahul
102 Ravi
101 Vijay
-----------Hash map-----------
100 Amit
101 Vijay
102 Rahul
104 Amit
```

本文由 **Aditya Goel** 整理。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论