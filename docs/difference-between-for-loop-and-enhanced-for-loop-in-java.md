# Java 中 for 循环和增强型 for 循环的区别

> 原文:[https://www . geeksforgeeks . org/for-loop 与增强型 for-loop-in-java 的区别/](https://www.geeksforgeeks.org/difference-between-for-loop-and-enhanced-for-loop-in-java/)

Java for-loop 是一个控制流语句，它多次迭代程序的一部分。For-loop 是 java 中最常用的循环。如果我们事先知道迭代的次数，那么 for-loop 是最好的选择。

**语法:**

```
for( initializationsection ; conditional check ;  increment/decrement section)
   {
    // Code to be executed
   }
```

> for 循环中的花括号是可选的，如果 for 循环中没有花括号，我们只能在 for 循环下使用一条语句，它不应该是声明性语句，如果我们在那里编写声明性语句，那么我们将会得到编译时错误。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the use of
// for loop

// Importing all input output classes
import java.io.*;
// Importing all classes from
// java.util package
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // 1st for-loop
        // Iteration ocer 5 elements using for loop
        for (int i = 1; i <= 5; i++) {

            // Print statement
            System.out.println("GFG!");
        }

        // 2nd for-loop
        // Declaring and initialization a variable
        // so we will get compile time error
        for (int i = 1; i <= 1; i++)
            int x = 0;
    }
}
```

**输出:**

**情况 1:** 缺少第二个 for-loop

```
GFG
GFG
GFG
GFG
GFG 
```

**情况 2:** 存在第二个 for-loop

```
prog.java:28: error: variable declaration not allowed here
         int x=0;
             ^
1 error 
```

**输出解释:**

*   在初始化部分，该部分在循环生命周期中只执行一次。在这里，我们可以为循环声明和初始化一个局部变量。在这里，我们可以声明任意数量的变量，但是应该错误地具有相同的类型。如果我们试图声明不同的数据类型，那么我们将得到编译**–**时间错误。在本节*、*中，我们可以使用任何有效的 java 语句，包括“*system . out . println()”*。
*   在条件检查期间，我们可以采用任何有效的 java 表达式，它应该是布尔类型。这部分是可选的，如果我们不取任何东西，那么*编译器将总是在这里放置一个真值。*
*   *在递增/递减部分，我们可以对初始化值进行递增或递减。在这一节中，我们可以使用任何有效的 java 语句，包括“*system . out . println()”*，这一节也是可选的。*

***环路增强(每个环路)***

*这个 for-loop 是在 java 版本中引入的 **d** ，它也是一个控制流语句，多次迭代程序的一部分。这个 for 循环提供了遍历数组或集合的另一种方式，因此它主要用于遍历数组或集合。这个循环还使代码更易读，减少了代码中出现错误的机会。*

***语法:***

```
*for(data-type variable : array | collection)
  {
   // Code to be executed
  }* 
```

***示例:***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java Program to show usage of for-each loop

// Importing all classes from
// java.uti package
// Importing all input output classes
import java.io.*;
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing the integer array
        // Custom integer entries in an array
        int[] array = { 1, 2, 3, 4, 5, 6 };

        // Accessing the element of array
        // using for-each loop
        for (int a : array) {
            // Print all elements of an array
            System.out.println(a);
        }
    }
}*
```

***Output**

```
1
2
3
4
5
6
```* 

*在可视化了这两个程序之后，我们发现了一些结论性的差异，这些差异以表格的形式描述出来，以便于我们更好地理解。*

<figure class="table">

| 正常 for 循环 | 增强的 for 循环 |
| --- | --- |
| 这个 for-loop 存在于 JDK1 中 | 该 for 循环来自 JDK5 |
| 在正常的 for 循环中，我们可以根据自己的意愿通过使用i=i+x(其中 x 是任何常数 x=1，2，3…) | 但是增强的 for 循环将以顺序方式执行，即计数器总是增加 1。 |
| 使用这个 for 循环，我们可以迭代任何容器对象。 | 我们只能通过使用这个循环来实现可迭代接口来迭代那个容器。 |
| 在这个 for 循环中，我们可以按照递减或递增的顺序进行迭代。 | 但是在这个 for 循环中，我们只能以递增的顺序迭代。 |
| 在这个 for 循环中，我们可以替换任何特定索引处的元素。 | 但是在这个 for 循环中，我们不能访问索引，所以我们不能在任何特定的索引中替换元素。 |
| 通过使用普通 for 循环，我们可以按原始顺序或相反顺序打印数组元素。 | 但是在 for-each 循环**、**中，我们只能按原始顺序打印数组元素，而不能按相反顺序打印 |
| **示例:**打印 1D 阵列中的元素int[ ] x={1，2，3 }；for(int I = 0；i{system . out . println(x[I])；

} | **示例:**使用 for-each 循环打印 1D 数组中的元素int[ ] x={1，2，3 }；for(int a : x){system . out . println(a)；} |
| **示例:**使用 for 循环打印 2D 数组中的元素int[ ][ ] x={{1，2，3}，{4，5，6 } }；for(int I = 0；ifor(int j = 0；jsystem . out . println(x[I][j])；}} | **示例:**使用 for-each 循环打印 2D 数组中的元素int[ ][ ] x={{1，2，3}，{4，5，6 } }；for(int[]x1:x){ 0for(int x2:x1){ 0system . out . println(x2)；}} |

</figure>