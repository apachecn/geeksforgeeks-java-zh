# Java 中的跳转语句

> 原文:[https://www.geeksforgeeks.org/jump-statements-in-java/](https://www.geeksforgeeks.org/jump-statements-in-java/)

跳转语句是将执行控制从程序中的一点转移到另一点的控制语句。Java 编程语言中提供了两个 Jump 语句:

1.  Break statement.

### break 语句

**1。使用中断语句退出循环:**

在 java 中，break 语句用于终止最近的循环语句或 switch 语句的执行。break 语句与 switch 语句一起广泛使用，**表示**循环，**表示**循环，**表示 do-while** 循环。

#### 语法:

```java
break;
```

当在循环中发现 **break** 语句时，循环终止，控制到达循环后面的语句。这里有一个例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the 
// break keyword in Java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int n = 10;
        for (int i = 0; i < n; i++) {
            if (i == 6)
                break;
            System.out.println(i);
        }
    }
}
```

**Output**

```java
0
1
2
3
4
5
```

如您所见，代码打算使用 for 循环打印 1 到 10 个数字，但它只打印 1 到 5 个。一旦 I 等于 6，控制就终止循环。

在 switch 语句中，如果缺少 **break** 语句，则每个**案例**标签都会执行到 switch 结束。

**2。使用中断作为转到**的一种形式

Java 没有 goto 语句，因为它产生了一种非结构化的方式来改变程序执行的流程。Java 展示了 break 语句的扩展形式。这种形式的**打破**与**这个标签一起工作。**标签是标识语句或代码块的标签的名称。

#### **语法:**

```java
break label;
```

当这种形式的**中断**执行时，控制跳出标记的语句或块。

这里举个例子:

T3】爪哇 T5

```java
// Java program to illustrate the 
// break keyword as a Goto statement in Java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        for (int i = 0; i < 3; i++) {
        one : { // label one
        two : { // label two
        three : { // label three
            System.out.println("i=" + i);
            if (i == 0)
                break one; // break to label one
            if (i == 1)
                break two; // break to label two
            if (i == 2)
                break three; // break to label three
        }
            System.out.println("after label three");
        }
            System.out.println("after label two");
        }
            System.out.println("after label one");
        }
    }
}
```

T6T8**输出**T1

在上面的程序中，当 i=0 时，第一个 if 语句成功，并导致一个 break 标记为 1，然后打印该语句。当 i=1 时，第二个 if 语句成功，并导致一个分隔符标记为 2，然后打印语句。当 i=2 时，第三个 if 语句成功，并导致中断，以标记三，然后打印所有三个语句。

### 继续语句

**continue** 语句推动循环的下一次重复发生，在它自己和控制循环的条件表达式之间跳转任何代码。

这里举个例子:

T3】爪哇 T5

```java
// Java program to illustrate the 
// continue keyword in Java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        for (int i = 0; i < 10; i++) {
            if (i == 6){
                  System.out.println();
                  // using continue keyword 
                  // to skip the current iteration
                continue;
            }
            System.out.println(i);
        }
    }
}
```

T6T8**输出**T1

在程序中，当 I 的值为 6 时，编译器会遇到 continue 语句，然后跳过 6。