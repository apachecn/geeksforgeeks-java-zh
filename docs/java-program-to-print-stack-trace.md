# Java 程序打印堆栈跟踪

> 原文:[https://www . geesforgeks . org/Java-程序到打印-堆栈-trace/](https://www.geeksforgeeks.org/java-program-to-print-stack-trace/)

考虑一个书架，里面的书一个放在另一个上面。现在，如果一个人想读他放在第一位的那本书，为了做到这一点，需要把第一本书上的所有书都拿走，以便拿到想要的那本书。这本书一开始就被放在第一位。计算机以这种方式存储被称为元素的书籍的方法被称为[堆栈](https://www.geeksforgeeks.org/stack-data-structure/)。

它是一种抽象数据类型，具有以下操作:

<figure class="table">

| 

操作

 | 

行动

 |
| --- | --- |
| 推送() | 插入元素 |
| 流行音乐() | 删除元素 |
| isEmpty() | 检查堆栈是否为空 |
| isFull（） | 检查堆栈是否已满 |
| 顶部()或 peek() | 要从堆栈中访问顶部元素 |

</figure>

现在根据[栈](https://www.geeksforgeeks.org/stack-class-in-java/)中的函数，一个  例外是在 3 种情况下抛出:

*   如果堆栈已满，则调用
*   弹出移除并返回栈顶的值。
*   如果调用 pop 时堆栈为空。

为了打印这个异常，有一种方法对这个数据结构称为[***【print stack trace()***](https://www.geeksforgeeks.org/throwable-printstacktrace-method-in-java-with-examples/)**。**用于特定异常的异常处理程序中，处理异常。这是 Java 可抛出类的一种方法，它打印可抛出异常对象以及其他信息，如发生异常的行号和发生异常的类名。[可投掷](https://www.geeksforgeeks.org/throwable-class-in-java-with-examples/)是所有异常类的超级类。

下面讨论两种堆栈跟踪:

1.  **单线堆叠轨迹**
2.  **多线堆栈跟踪**

**A .单行堆栈跟踪:**大多数通用异常都属于这一类。有几个例外，但为了实现，考虑了部分 [*的*](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/) 数组

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Importing Classes/Files
import java.io.*;

class GFG {

    // Main Driver Method
    public static void main(String[] args)
    {
        // Inserting elements into array
        int a[] = { 1, 2, 3 };

        // Try-Catch Block
        try {
            // Exception occurs
            System.out.println(a[5]);
        }

        // Try-Catch Block
        catch (ArrayIndexOutOfBoundsException e) {

            // Printing Exception Object as well as
            // the line where Exception occur
            e.printStackTrace();
        }
    }
}
```

**运行时错误:**

```
java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 3
    at GFG.main(File.java:9)
```

**b . Multi**–**行堆栈跟踪:**当我们将内部函数调用到另一个函数中时，如果任何函数抛出异常，则使用[*print Stack Trace()*](https://www.geeksforgeeks.org/throwable-printstacktrace-method-in-java-with-examples/)方法追溯其调用的所有路径，就会出现这种情况。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Importing Classes/Files
import java.io.*;

class GFG {

    // Creating random function to test
    static void check2()
    {
        // Try-catch block for exception
        try {

            int a = 5 / 0;
            // Exception occur as logically
            // In math '/' operatop satisfies x/y where y!=0
        }

        // Catch Block to catch exception if occurs
        catch (Exception e) {

            // retrace all the path where this function call
            e.printStackTrace();
        }
    }

    // calling  the function check2()
    static void check() { check2(); }

    // Driver Main Method
    public static void main(String[] args)
    {
        check(); // calling the function check()
    }
}
```

**运行时错误:**

```
java.lang.ArithmeticException: / by zero
    at GFG.check2(File.java:11)
    at GFG.check(File.java:7)
    at GFG.main(File.java:19)
```