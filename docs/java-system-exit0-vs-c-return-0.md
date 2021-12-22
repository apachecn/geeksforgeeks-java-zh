# Java system . exit(0)vs c++ return 0

> 原文:[https://www . geesforgeks . org/Java-system-exit 0-vs-c-return-0/](https://www.geeksforgeeks.org/java-system-exit0-vs-c-return-0/)

Java 和 C++是具有不同应用和设计目标的语言。C++是过程编程语言 C 的扩展，Java 依赖于 Java 虚拟机来实现安全性和高度可移植性。这导致他们有许多不同。在本文中，我们将看到 *C++返回 0* 和 *Java System.exit(0)* 的区别。在讨论这些差异之前，让我们先了解它们各自的真正含义。

### C++返回 0

*   在标准 C++中，建议创建一个带有返回类型的 *main()* 函数。
*   所以， *main()* 函数必须返回一个整数值，这个整数值通常是要传递回操作系统的值。

在 *stdlib.h* 中，宏*退出 _ 成功*和*退出 _ 失败*是这样定义的:

```java
#define EXIT_SUCCESS    0
#define EXIT_FAILURE    1

```

*   **返回 0–>**成功终止。
*   **返回 1** 或任何其他**非零**值–>不成功终止。
*   返回不同的值，如**返回 1** 或**返回-1** 或任何其他**非零**值意味着程序返回错误。

## C++

```java
#include <iostream>

using namespace std;

int main()
{
    int num1, num2;
    cin >> num1 >> num2;
    cout << num1 + num2;

    return 0;
}
```

```java
Input:
54
4

Output:
58

```

### Java System.exit(0)

首先要考虑的是**Java 中的主函数有一个返回类型 *void* 。**

*   **在 Java 中，您不能返回退出代码，因为它是一个 void 函数。所以，如果要明确指定退出代码，就必须使用 *System.exit()* 方法。**
*   ***java.lang.System.exit()* 方法通过终止运行 java 虚拟机退出当前程序。**

****Java . lang . system . exit()方法的声明:****

```java
public static void exit(int status)
**exit(0) -->**successful termination.
**exit(1)** or **exit(-1)** or any other non-zero value –-> unsuccessful termination. 
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        System.out.println("GeeksForGeeks");
    }
}
```

```java
**Output:**
GeeksforGeeks
```

****注:**两个*返回 0* 和*系统.退出(0)* 的工作与*主()*功能返回类型的区别相同。**

****下表描述了差异:****

<figure class="table">

| SR.NO | C++返回 0 | Java System.exit(0) |
| --- | --- | --- |
| 1. | C++中的 main()函数有一个返回类型。因此，C++中的每个主方法都应该返回值。 | java 中的 main()方法属于 void 返回类型。因此，main 方法不应该返回值。 |
| 2. | 在 C++程序中，return 0 语句是可选的:编译器会自动在程序中隐式添加 return 0。 | 在 Java 中，调用 System.exit(0)或显式添加它没有特殊要求。 |
| 3. | 它是一个用来返回值的关键字，所以不需要任何声明。它只需要返回带有值或变量的关键字。 | java.lang.System.exit()方法的声明:*公共静态无效退出(int 状态)* |
| 4. | 通常，return 0 用于向操作系统返回退出代码。 | 如果我们想明确指定操作系统的退出代码，我们必须使用 System.exit()。 |
| 5. | 在 C++程序中使用 return 0 被认为是一种很好的做法。 | 实际上避免使用 System.exit(0)，因为我们的 main()方法带有 void 返回类型。 |

</figure>