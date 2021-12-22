# Java 三元运算符拼图

> 原文:[https://www.geeksforgeeks.org/java-ternary-operator-puzzle/](https://www.geeksforgeeks.org/java-ternary-operator-puzzle/)

找到程序的输出

```java
public class GFG {
    public static void main(String[] args) {
    char x = 'X';
    int i = 0;
    System.out.print(true ? x : 0);
    System.out.print(false ? i : x);
    }
}
```

**解决方案:**
运行程序，发现它打印 **X88** 。第一个打印语句打印 X，第二个打印 88。

确定条件表达式结果类型的规则太长太复杂，无法完整再现，但这里有三个要点。

1.  如果第二个和第三个操作数具有相同的类型，那就是条件表达式的类型。换句话说，你可以通过避开混合类型计算来避免整个混乱。
2.  如果其中一个操作数是 T 类型，其中 T 是字节、短或字符，而另一个操作数是 int 类型的常量表达式，其值可在 T 类型中表示，则条件表达式的类型是 T
3.  否则，二进制数值提升将应用于操作数类型，条件表达式的类型是第二个和第三个操作数的提升类型。

第二点和第三点是这个谜题的关键。在程序中的两个条件表达式中，一个操作数是 char 类型，另一个是 int 类型。在这两个表达式中，int 操作数的值都是 0，可以表示为一个字符。但是，只有第一个表达式中的 int 操作数是常量(0)；第二个表达式中的 int 操作数是变量(I)。因此，第 2 点适用于第一个表达式，其返回类型是 char。第 3 点适用于第二个条件表达式，它的返回类型是对 int 和 char 应用二进制数字提升的结果，也就是 int。

条件表达式的类型决定了调用打印方法的哪个重载。对于第一个表达式，调用[print stream . print](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)(char)；对于第二个，PrintStream.print(int)。前者重载将变量 X 的值打印为 Unicode 字符(X)，而后者将其打印为十进制整数(88)。

本文由 **Shubham Juneja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。