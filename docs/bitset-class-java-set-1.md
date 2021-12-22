# Java.util.BitSet 类在 Java 中用示例| Set 1

> 原文:[https://www.geeksforgeeks.org/bitset-class-java-set-1/](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

**BitSet** 是 java.util 包中定义的一个类。它创建一个由布尔值表示的位数组。

**施工人员:**

```java
 BitSet class Constructors
    /                  \ 
 BitSet()          BitSet(int no_Of_Bits)
```

*   **BitSet() :** 创建空 BitSet 对象的无参数构造函数。

*   **位集(int no_Of_Bits):** 具有整数参数的单构造函数，用于创建位集类的实例，整数参数的初始大小表示位数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program illustrating Bitset Class constructors.
import java.util.*;
public class GFG
{
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet(6);

        /* set is BitSet class method
           explained in next articles */
        bs1.set(0);
        bs1.set(1);
        bs1.set(2);
        bs1.set(4);

        // assign values to bs2
        bs2.set(4);
        bs2.set(6);
        bs2.set(5);
        bs2.set(1);
        bs2.set(2);
        bs2.set(3);

        // Printing the 2 Bitsets
        System.out.println("bs1  : " + bs1);
        System.out.println("bs2  : " + bs2);
    }
}
```

输出:

```java
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6}
```

**要点:**

*   阵列的大小是灵活的，可以根据需要增加以容纳额外的位。
*   因为它是一个数组，所以索引是从零开始的，位值只能由非负整数作为索引来访问。
*   BitSet 的默认值是布尔值 false，表示为 0(关闭)。
*   调用 clear 方法会将位值设置为 false。
*   bitest 每个布尔值使用大约 1 位。
*   要访问位集中的特定值，get 方法与整数参数一起用作索引。

**如果位集中的数组索引设置为负数会发生什么？**

程序将抛出 Java . lang . negativeraysizeexception

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program illustrating Exception when we access
// out of index in BitSet class.
import java.util.*;

public class GFG
{
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();

        // Negative array size
        BitSet bs2 = new BitSet(-1);

        /* set is BitSet class method
           explained in next articles */
        // assigning values to bitset 1
        bs1.set(0);
        bs1.set(1);

        // assign values to bs2
        bs2.set(4);
        bs2.set(6);

        System.out.println("bs1  : " + bs1);
        System.out.println("bs2  : " + bs2);
    }
}
```

输出:

```java
Exception in thread "main" java.lang.NegativeArraySizeException: nbits < 0: -1
    at java.util.BitSet.(BitSet.java:159)
    at GFG.main(NewClass.java:9)
```

[Java 中的 BitSet 类方法，带示例| Set 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。