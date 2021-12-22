# 【Java 支持 goto 吗？

> 原文:[https://www.geeksforgeeks.org/g-fact-64/](https://www.geeksforgeeks.org/g-fact-64/)

Java 不支持 goto，它被保留为一个关键字，以防他们想将其添加到更高的版本中。

*   与 C/C++不同，java 没有 goto 语句，但是 Java 支持**标签**。
*   标签在 Java 中唯一有用的地方就是嵌套循环语句之前。
*   我们可以用 break 来指定标签名，以打破一个特定的外部循环。
*   同样，可以用 continue 指定标签名。

**在 Java 中使用带标签的 break】**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// using label  and break
// instead of goto

// file name: Main.java
public class Main {
    public static void main(String[] args)
    {

    // label for outer loop
    outer:
        for (int i = 0; i < 10; i++) {
            for (int j = 0; j < 10; j++) {
                if (j == 1)
                    break outer;
                System.out.println(" value of j = " + j);
            }
        } // end of outer loop
    } // end of main()
} // end of class Main
```

**Output:** 

```
value of j = 0
```

**使用 Java 中的继续标签**

我们也可以用 continue 代替 break。参见以下程序示例。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// using label  and continue
// instead of goto

// file name: Main.java
public class Main {
    public static void main(String[] args)
    {

    // label for outer loop
    outer:
        for (int i = 0; i < 10; i++) {
            for (int j = 0; j < 10; j++) {
                if (j == 1)
                    continue outer;
                System.out.println(" value of j = " + j);
            }
        } // end of outer loop
    } // end of main()
} // end of class Main
```

**Output:** 

```
value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
 value of j = 0
```

**解释:**由于 continue 语句会跳到循环中的下一次迭代，所以当我从 0 迭代到 9 时，它会迭代 10 次。因此，外部循环执行 10 次，内部 for 循环在每个外部循环中执行 1 次。
Java 没有 goto 语句，因为它提供了一种以任意和非结构化方式进行分支的方法。这通常会使 goto-rided 代码难以理解和维护。它还禁止某些编译器优化。然而，在一些地方，goto 对于流控制来说是一个有价值且合法的构造。例如，当您退出一组深度嵌套的循环时，goto 会很有用。为了处理这种情况，Java 定义了 break 语句的扩展形式。
标记中断语句的一般形式是:

```
break label;
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code
public class Label_Break1 {

    public static void main(String[] args)
    {

        boolean t = true;
    first : {
    second : {
    third : {
        System.out.println("Before the break");
        if (t) // break out of second block
            break second;
    }
        System.out.println("This won't execute");
    }
        System.out.println("This is after the second block");
    }
    }
}
// This code is contributed by Sagar Gupta
```

**Output:** 

```
Before the break
This is after the second block
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code
public class Label_Break2 {

    public static void main(String[] args)
    {

    outer:
        for (int i = 0; i < 3; i++) // label
        {
            System.out.print("Pass " + i + ": ");
            for (int j = 0; j < 100; j++) {
                if (j == 10) {
                    break outer; // Exit both loops
                }
                System.out.print(j + " ");
            }
            System.out.println("This will not be printed");
        }
        System.out.println("Loops Complete.");
    }
}
// This code is contributed by Sagar Gupta
```

**Output:** 

```
Pass 0: 0 1 2 3 4 5 6 7 8 9 Loops Complete.
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。