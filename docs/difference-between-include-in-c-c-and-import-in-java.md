# C/c++中的#include 和 JAVA 中的 import 的区别

> 原文:[https://www . geesforgeks . org/include-in-c-c 和 import-in-java 之间的区别/](https://www.geeksforgeeks.org/difference-between-include-in-c-c-and-import-in-java/)

[**# include In C/c++**](https://www.geeksforgeeks.org/c-c-include-directive-with-examples/)**:**在 [C 语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/)的情况下， **#include** 是程序中的标准或用户自定义文件，它告诉预处理器将另一个文件的内部内容插入到程序的源代码中。

**语法:**

> #包括<stdio.h></stdio.h>

**程序 1:**
下面是一个 C 程序来演示**的使用#包括**:

## C

```
// C Program to demonstrate use of #include
#include <stdio.h>

// Header file loads all the
// necessary Input output
// file at beginning only

// Driver Code
int main()
{
    printf("GeeksforGeeks");
    return 0;
}
```

**Output:**

```
GeeksforGeeks

```

[**在 Java 中导入**](https://www.geeksforgeeks.org/packages-in-java/) **:** 在 [JAVA](https://www.geeksforgeeks.org/java/) 中， **import** 语句用于加载整个包或包中的某些类。它写在类定义之前和包语句之后(如果有的话)。

**语法:**

> 导入 Java . util . *；

**程序 2:**
下面是一个 Java 程序来演示使用**导入**语句:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate use of import
import java.io.*;

// import statement doesn't load
// all the necessary files at
// beginning rather it loads
// only those files which it
// needs at the runtime
class GFG {
    public static void main(String[] args)
    {
        System.out.println("GeeksforGeeks");
    }
}
```

**Output:**

```
GeeksforGeeks

```

C/C++ 中的 **#include 和 Java 中的**import**都是用来加载预定义的头文件或包的，但有一定的区别，如下所列:**

<figure class="table">

| **序列号** | **#包含在 C/C++** 中 | **用 Java 导入** |
| **1** | 必须使用 **#include** 语句来包含标准头文件。 | **用 java 导入**语句是可选的 |
| **2** | 它只在开始时加载文件。 | 开始时不会加载任何类文件。
每当使用一个特定的类时，将只加载相应的类文件。 |
| **3** | 不必要的内存和处理器时间浪费。 | 没有这样浪费内存和处理器的时间。 |
| **4** | 程序的大小增加。 | 不增加程序的大小。 |
| **5** | 它也被称为静态包含。 | 它也被称为动态包含。 |

</figure>