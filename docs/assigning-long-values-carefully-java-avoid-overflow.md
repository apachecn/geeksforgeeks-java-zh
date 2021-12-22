# 在 Java 中小心分配长值以避免溢出

> 原文:[https://www . geesforgeks . org/赋值-长值-小心-Java-避免-溢出/](https://www.geeksforgeeks.org/assigning-long-values-carefully-java-avoid-overflow/)

预测以下程序的输出

```java
public class LongDivision {
    public static void main(String[] args) {
    final long MICROS_PER_DAY = 24 * 60 * 60 * 1000 * 1000;
    final long MILLIS_PER_DAY = 24 * 60 * 60 * 1000;
    System.out.println(MICROS_PER_DAY / MILLIS_PER_DAY);

    }
}
```

**解决方案:**

除数和被除数都是 long 类型的，它很容易大到足以容纳任一乘积而不溢出。看来，这个程序必须打印 1000 份。可惜打印 **5** 。这到底是怎么回事？问题是常数 MICROS_PER_DAY 的计算确实溢出了。虽然计算的结果适合一长串，但不适合一个整数。计算完全是在整数运算中进行的，只有在计算完成后，结果才会被提升为 long。到那时，已经太晚了:计算已经溢出来了。
从 int 到 long 的提升是一种扩展的原语转换，保留了(不正确的)数值。然后，该值除以 MILLIS _ PER _ DAY，计算正确，因为它符合 int。这个除法的结果是 5。那么为什么计算是在整数运算中进行的呢？因为所有相乘的因子都是 int 值。
将两个 int 值相乘，得到另一个 int 值。 **Java 没有目标类型，这是一种语言特性，其中存储结果的变量的类型会影响计算的类型**。通过在每个产品中使用长文字代替 int 作为第一要素，很容易修复程序。这迫使表达式中的所有后续计算都用长算术来完成。虽然只需要在 MICROS_PER_DAY 的表达式中这样做，但是在两个产品中都这样做是很好的形式。
同样，在产品中使用 long 作为第一个值并不总是必要的，但是这样做是很好的形式。用长值开始这两个计算清楚地表明它们不会溢出。该程序按预期打印 1000 张:

```java
public class LongDivision {
    public static void main(String[] args) {
    final long MICROS_PER_DAY = 24L * 60 * 60 * 1000 * 1000;
    final long MILLIS_PER_DAY = 24L * 60 * 60 * 1000;
    System.out.println(MICROS_PER_DAY / MILLIS_PER_DAY);

    }
}
```

输出:

```java
1000

```

教训很简单:**处理大数时，要注意溢出——它是无声的杀手。**

本文由 **Shubham Juneja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。