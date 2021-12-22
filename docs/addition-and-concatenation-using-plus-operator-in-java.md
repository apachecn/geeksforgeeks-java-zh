# Java 中使用+运算符的加法和串联

> 原文:[https://www . geesforgeks . org/add-and-concation-use-plus-operator-in-Java/](https://www.geeksforgeeks.org/addition-and-concatenation-using-plus-operator-in-java/)

到目前为止，在 Java 中，我们一直在玩整数部分，我们见证了+运算符的行为方式与它应该的方式相同，因为十进制系统在二进制级别上向下累加，结果二进制数在控制台上以通用十进制系统抛出。但是极客们甚至想知道如果我们在整数和字符串之间使用这个+运算符会怎么样。

**示例**

## Java

```java
// Java Program to Illustrate Addition and Concatenation

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Print statements to illustrate
        // addition and Concatenation 
        // using + operators over string and integer
        // combination
        System.out.println(2 + 0 + 1 + 6 + "GeeksforGeeks");
        System.out.println("GeeksforGeeks" + 2 + 0 + 1 + 6);
        System.out.println(2 + 0 + 1 + 5 + "GeeksforGeeks" + 2 + 0 + 1 + 6);
        System.out.println(2 + 0 + 1 + 5 + "GeeksforGeeks" + (2 + 0 + 1 + 6));
    }
}
```

**输出**

```java
9GeeksforGeeks
GeeksforGeeks2016
8GeeksforGeeks2016
8GeeksforGeeks9
```

**输出解释:**这种不可预测的输出是由于编译器从左到右计算给定的表达式，给定的运算符具有相同的优先级。一旦遇到字符串，它会将表达式的其余部分视为字符串(同样基于表达式的优先顺序)。

```java
System.out.println(2 + 0 + 1 + 6 + "GeeksforGeeks");  
```

*打印等于 9 的 2，0，1 和 6 的相加*T0

*它打印 2，0，1 和 6 的连接，这是 2016 年，因为它最初遇到字符串。基本上，字符串优先，因为它们比整数具有更高的转换优先级。*

```java
System.out.println(2 + 0 + 1 + 5 + "GeeksforGeeks" + 2 + 0 + 1 + 6); 
```

*打印 2，0，1 和 5 的相加，而 2，0，1 和 6 的拼接*是基于上面给出的*示例的*。**

```java
*System.out.println(2 + 0 + 1 + 5 + "GeeksforGeeks" + (2 + 0 + 1 + 6));* 
```

*由于**将( )的优先级置于+之上，因此它打印出了基于 2，0，1 和 5 以及 2，0，1 和 6 的* *的加法。因此，首先计算( )中的表达式，然后进行进一步评估。*

本文由**普拉哈尔·马图尔供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。