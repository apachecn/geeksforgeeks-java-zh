# 浮点运算&C、C++和 Java 中的关联性

> 原文:[https://www . geesforgeks . org/g-fact-39-浮点运算-关联性/](https://www.geeksforgeeks.org/g-fact-39-floating-point-operations-associativity/)

浮点运算遵循结合性吗？换句话说，对于表达式“(A + B) + C”和“A + (B + C)”我们总是得到相同的结果吗

人们可能期望浮点数在编程语言中遵循结合律，因为它们在数学上是关联的。然而，并非所有情况都是如此。

下面考虑 C/C++程序。

```
// C/C++ program to demonstrate that floating point
// addition may not be associative.
#include<stdio.h>
int main()
{
    // A and B have sane values but apposite signs
    float A = -500000000;
    float B =  500000000;

    float C = 1;

    printf("A + (B + C) is equal to %f \n", A + (B + C));
    printf("(A + B) + C is equal to %f", (A + B) + C);

    return 0;
}
```

输出:

```
A + (B + C) is equal to 0.000000 
(A + B) + C is equal to 1.000000
```

从上面给出的输出可以明显看出，浮点运算并不是在所有情况下都遵循结合律。这是由于浮点数的存储和表示格式，它在计算过程中舍入数字，因此，代数的关联定律不一定适用于浮点数。在这种情况下，

```
Explanation for above output:

A + (B + C):
(B + C) = 500000000.0 + 1.0
        = 500000000.0 
(rounded off during floating point arithmetic)

A + (B + C) = -500000000.0 + 500000000.0 
            =  0.000000

(A + B) + C:
(A + B) = -500000000.0 + 500000000.0 
        = 0.000000

(A + B) + C = 0.000000 + 1 
            = 1.000000

```

【Java 怎么样？
我们在 Java 中得到相同的结果，因为 Java 也对浮点数使用类似的表示。

```
// Java program to demonstrate that floating-point
// addition may not be associative
import java.io.*;

class Main
{
    public static void main (String[] args)
    {
        // A and B have sane values but apposite signs
        float A = -500000000;
        float B =  500000000;

        float C = 1;

        System.out.println("A + (B + C) is equal to " + 
                          (A + (B + C)));
        System.out.println("(A + B) + C is equal to " + 
                          ((A + B) + C));
    }
}
```

输出:

```
A + (B + C) is equal to 0.000000 
(A + B) + C is equal to 1.000000
```

**整数怎么样？**
现在让我们在数据类型为整数时尝试同样的计算。这里有一段代码供您观察:

```
#include<stdio.h>
#include<stdio.h>
int main()
{
   // A and B have sane values but apposite signs
   int A = -500000000;
   int B =  500000000;

   int C = 1;

   printf(" A + (B + C) is equal to %d \n", A + (B + C));
   printf("(A + B) + C is equal to %d", (A + B) + C);

   return 0;
}
```

输出:

```
 A + (B + C) is equal to 1 
(A + B) + C is equal to 1
```

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论