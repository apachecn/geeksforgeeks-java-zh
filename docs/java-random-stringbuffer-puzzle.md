# 一个 Java 随机和字符串填充难题

> 原文:[https://www . geesforgeks . org/Java-random-stringbuffer-拼图/](https://www.geeksforgeeks.org/java-random-stringbuffer-puzzle/)

预测程序的输出

```
import java.util.Random;
public class GFG {
    private static Random rd = new Random(); 
    public static void main(String[] args) {
    StringBuffer word = null;
    switch(rd.nextInt(2)) {
        case 1: word = new StringBuffer('P');
        case 2: word = new StringBuffer('G');
        default: word = new StringBuffer('M');
    }
    word.append('a');
    word.append('i');
    word.append('n');
    System.out.println(word);
    }
}
```

**解决方案:**
乍一看，这个程序可能会以相同的可能性打印出痛苦、收获和主要这几个词，每次运行的可能性不同。但是程序的输出总是 **ain** 。
三个 bug 共同导致了这种行为。让我们分别看看:-
**1。** rd.nextInt(2)将返回 0(包括 0)和 2(不包括 0)之间的数字，即 0 和 1。因此，我们的程序从不打印“疼痛”。

**2。**第二个 bug 是案例之间没有 break 语句。无论 switch 表达式的值是多少，程序都将执行该案例和所有后续案例。每种情况都给变量单词赋值，最后一次赋值获胜。最后一个赋值将始终是最后一个情况下的赋值(默认)，它是新的 StringBuffer('M ')。这表明该程序也永远不会打印“增益”。

**3。**最后一个也是最微妙的 bug 是，表达式 new StringBuffer('M ')可能不会像您认为的那样。没有 StringBuffer(char)构造函数。但是有一个用整数表示它的初始容量。在这种情况下，编译器选择 int 构造函数，应用扩展原语转换将字符值“M”转换为 int 值 77。换句话说，
new StringBuffer(' M ')返回一个初始容量为 77 的空字符串缓冲区。程序的剩余部分将字符 a、I 和 n 追加到空字符串缓冲区，并打印出其内容，这些内容始终是' ain '。

本文由 **Shubham Juneja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。