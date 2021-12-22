# Java 中的中断和继续语句

> 原文:[https://www . geesforgeks . org/break-and-continue-statement-in-Java/](https://www.geeksforgeeks.org/break-and-continue-statement-in-java/)

break 和 continue 语句是跳转语句，用于跳过循环中的一些语句，或者在不检查测试表达式的情况下立即终止循环。这些语句可以在任何[循环](https://www.geeksforgeeks.org/loops-in-java/)中使用，例如 for、while、do-while 循环。

[**Break**](https://www.geeksforgeeks.org/break-statement-in-java/)**:**Java 中的 Break 语句用于从循环中立即终止。当在循环中遇到 break 语句时，循环迭代就此停止，控制立即从循环返回到循环后的第一条语句。基本上，break 语句用于我们不确定循环的实际迭代次数的情况，或者我们想要基于某种条件终止循环的情况。

**语法:**

```
break;
```

在 Java 中，break 语句主要用于:

*   退出循环。
*   用作 goto 的“文明”形式。
*   在 switch 语句中终止一个序列。

**使用中断退出循环**

使用 break，我们可以绕过条件表达式和循环体中的任何剩余代码，强制立即终止循环。当我们在嵌套循环中使用 break 时，它只会从最里面的循环中断开。

**示例:**

## Java

```
// Java program to demonstrate using
// break to exit a loop
class GFG {
    public static void main(String[] args)
    {
        // Initially loop is set to run from 0-9
        for (int i = 0; i < 10; i++) {
            // Terminate the loop when i is 5
            if (i == 5)
                break;
            System.out.println("i: " + i);
        }
        System.out.println("Out of Loop");
    }
}
```

**输出**

```
i: 0
i: 1
i: 2
i: 3
i: 4
Out of Loop
```

**使用 break 作为 Goto 的一种形式**

Java 没有 goto 语句，因为它提供了一种以任意和非结构化方式进行分支的方法。Java 使用一个标签。标签用于识别代码块。

**语法:**

```
label:
{
  statement1;
  statement2;
  statement3;
  .
  .
}
```

现在，break 语句可以用来跳出目标块。我们不能打断任何没有为封闭块定义的标签。

**语法:**

```
break label;
```

**示例:**

## Java

```
// Java program to demonstrates using break with goto
class GFG {
    public static void main(String args[])
    {
    // First label
    first:
        for (int i = 0; i < 3; i++) {
        // Second label
        second:
            for (int j = 0; j < 3; j++) {
                if (i == 1 && j == 1) {

                    // Using break statement with label
                    break first;
                }
                System.out.println(i + " " + j);
            }
        }
    }
}
```

**输出**

```
0 0
0 1
0 2
1 0
```

**在 switch 语句中使用 break 终止一个序列。**

[开关语句](https://www.geeksforgeeks.org/switch-statement-in-java/)是多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行分派到代码的不同部分。break 语句在开关内部用于终止语句序列。break 语句是可选的。如果省略，执行将继续到下一个案例。

**语法:**

```
switch (expression)
{
  case value1:
    statement1;
    break;
  case value2:
    statement2;
    break;
  .
  .
  case valueN:
    statementN;
    break;
  default:
    statementDefault;
}
```

**示例:**

## Java

```
// Java program to demonstrate using break to terminate a
// sequence in a switch statement.
class GFG {
    public static void main(String args[])
    {
        int i = 2;
        switch (i) {
        case 0:
            System.out.println("i is zero.");
            break;
        case 1:
            System.out.println("i is one.");
            break;
        case 2:
            System.out.println("i is two.");
            break;
        default:
            System.out.println("Invalid number");
        }
    }
}
```

**输出**

```
i is two.
```

**继续:**

Java 中的 continue 语句用于跳过循环的当前迭代。我们可以在任何类型的循环中使用 continue 语句，例如 for、while 和 do-while 循环。基本上，continue 语句用于我们想要继续循环，但不想要 continue 语句之后的剩余语句的情况。

**语法:**

```
continue;
```

**使用继续继续循环**

使用 continue，我们可以跳过循环的当前迭代，并立即跳到循环的下一个迭代。

**示例:**

## Java

```
// Java program to demonstrates the continue
// statement to continue a loop
class GFG {
    public static void main(String args[])
    {
        for (int i = 0; i < 10; i++) {
            // If the number is 2
            // skip and continue
            if (i == 2)
                continue;

            System.out.print(i + " ");
        }
    }
}
```

**输出**

```
0 1 3 4 5 6 7 8 9
```

**使用继续作为标记的继续语句**

未标记的 continue 语句用于继续最内部的循环。然而，由于 JDK 1.5 java 引入了另一个被称为标记继续语句的特性。我们可以使用带标签的 continue 语句来继续最外面的循环。

**示例:**

## Java

```
// Java program to demonstrates labeled continue statement
class GFG {
    public static void main(String args[])
    {
    // First label
    first:
        for (int i = 0; i < 3; i++) {
        // Second label
        second:
            for (int j = 0; j < 3; j++) {
                if (i == 1 && j == 1) {

                    // Using continue statement with label
                    continue first;
                }
                System.out.println(i + " " + j);
            }
        }
    }
}
```

**输出**

```
0 0
0 1
0 2
1 0
2 0
2 1
2 2
```

**中断和继续的区别:**

<figure class="table">

| 

**Break**

 | 

**Continue**

 |
| --- | --- |
| Break 语句用于立即终止循环。 | continue 语句用于跳过循环的当前迭代。 |
| break 关键字用于表示 java 编程中的 break 语句。 | continue 关键字用于表示 java 编程中的 continue 语句。 |
| 我们可以用 break with switch 语句。 | 我们不能用一个 continue with switch 语句。 |
| break 语句提前终止整个循环。 | continue 语句提前带来下一次迭代。 |
| 它停止循环的执行。 | 不停止循环的执行。 |

</figure>