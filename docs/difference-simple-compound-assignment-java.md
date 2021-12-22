# Java 中简单赋值和复合赋值的区别

> 原文:[https://www . geesforgeks . org/difference-simple-compound-assignment-Java/](https://www.geeksforgeeks.org/difference-simple-compound-assignment-java/)

许多程序员认为“x += i”这句话只是“x = x + i”的简写。这不完全正确。这两个语句都是赋值表达式。第二个语句使用简单赋值运算符(=)，而第一个语句使用复合赋值运算符。复合赋值运算符有+=、-=、*=、/=、%=等。
Java 语言规范说复合赋值 E1 op= E2 相当于简单赋值，
**E1 = (T) ((E1) op (E2))，其中 T 是 E1 的类型。**
换句话说，复合赋值表达式会自动将它们执行的计算结果转换为左侧的变量类型。如果结果的类型与变量的类型相同，则强制转换无效。但是，如果结果的类型比变量的类型更宽，复合赋值运算符将执行静默收缩基元转换。尝试执行等效的简单赋值将生成编译错误。

考虑下面的例子-

```
// A Java program that uses compound assignment
// for different types.
class GFG{
    public static void main(String s[]) {
    short x = 0;
    int i = 123456;
    x += i;  // Casts result to short
    System.out.println(x);
  }
}
```

输出:

```
-7616

```

在此语句执行后，您可能期望 x 的值为 123456，但事实并非如此；是-7616。int 值 123456 太大，短时间内无法容纳。自动生成的强制转换。它会无声地移除 int 值的两个高位字节。

```
// A Java program that uses simple addition
// for different types.
class GFG{
  public static void main(String s[]) {
    short x = 0;
    int i = 123456;
    x = x + i; // Causes compilation error
    System.out.println(x);
  }
}
```

输出:

```
prog.java:5: error: incompatible types: possible 
lossy conversion from int to short
x = x + i;
    ^
```

从上面的例子可以清楚地看出，复合赋值表达式可能会导致不希望的结果，对于像字节、短或字符这样的类型应该谨慎使用。如果我们使用它们，我们必须确保右边的表达式的类型没有更高的精度。

本文由 [**舒巴姆·朱尼加**](https://auth.geeksforgeeks.org/profile.php?user=shubhamjuneja11) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。