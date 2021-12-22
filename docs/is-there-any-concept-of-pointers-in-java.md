# C/C++指针对 Java 引用

> 原文:[https://www . geesforgeks . org/Java 中有指针概念吗/](https://www.geeksforgeeks.org/is-there-any-concept-of-pointers-in-java/)

**Java 没有指针；Java 有引用。**
**Reference:**Reference 是指其他事物的变量，可以用作那个其他事物的别名。
**指针:**指针是存储内存地址的变量，目的是作为存储在该地址的别名。
所以，指针是引用，但引用不一定是指针。指针是引用概念的一种特殊实现，这个术语往往只用于那些可以直接访问内存地址的语言。

**我们来讨论一些关于 C/C++和 Java 环境下指针和引用的要点:**

*   **C/C++允许指针运算，但 Java Pointers (References)不允许:**术语“指针”与指针的 C/C++概念有很强的关联，指针是存储内存地址的变量，可以通过算术修改指向任意地址。
    在 Java 中，指针只作为引用的实现细节存在。引用的副本被复制到被调用函数的堆栈中，指向与调用函数相同的对象，并允许您操作该对象。但是，您不能更改调用函数引用的对象。
*   **Java 不显式支持指针，但是 Java 隐式使用指针:** Java 使用指针来操作引用，但是这些指针不可用于外部使用。该语言隐式完成的任何操作实际上都是不可见的。
*   **指针可以做算术，引用不能**:通过指针算术进行内存访问从根本上来说是不安全的，为了安全防护，Java 有一个健壮的安全模型，因此不允许指针算术。无论情况如何，用户都不能操作指针。
*   **指向对象:**在 C 语言中，我们可以加减一个指针的地址来指向事物。在 Java 中，一个引用只指向**一件事**。您可以让一个变量保存不同的引用，但是这种对指针的 c 操作是不可能的。
*   **引用是强类型的:**引用的类型在 Java 中比指针的类型在 C 中受到更严格的控制。在 C 中，您可以有一个 int*并将其转换为 char*并重新解释该位置的内存。这种重新解释在 Java 中不起作用:您只能将引用另一端的对象解释为已经存在的对象(即，只有当指向的对象实际上是字符串时，您才能将对象引用转换为字符串引用)。
*   **操纵指针可能很危险:**一方面，用户控制指针可能很好，也很灵活，但也可能很危险。它们可能会成为问题的一大根源，因为如果使用不当，它们很容易打破代码是围绕它构建的假设。错误地使用它们是很容易的。

所以总的来说，Java 没有指针(在 C/C++的意义上)，因为它不需要指针来进行通用的面向对象编程。此外，向 Java 添加指针会破坏安全性和健壮性，并使语言更加复杂。

**说明指针操作的 CPP 程序**

```java
// A simple CPP program to illustrate 
// the concept of pointers and 
// their manipulations in C/C++
#include <iostream>
using namespace std;

int main()
{
   int number = 88;    
   int * pNumber;  

   // assign the address of the variable number 
   // to pointer pNumber
   pNumber = &number;  

   // Print content of pNumber 
   cout << pNumber << endl;  

   // Print address of number
   cout << &number << endl;  

   // Print value pointed to by pNumber
   cout << *pNumber << endl; 

   // Print value of number
   cout << number << endl;   

   // Re-assign value pointed to by pNumber
   *pNumber = 99;            
   cout << pNumber << endl;  
   cout << &number << endl;  
   cout << *pNumber << endl; 
   cout << number << endl;  

   cout << &pNumber << endl; 
}
```

输出:

```java
0x7fff1ae7ca94
0x7fff1ae7ca94
88
88
0x7fff1ae7ca94
0x7fff1ae7ca94
99
99
0x7fff1ae7ca98

```

**Java 程序说明参考文献**

```java
// A simple Java program 
// to illustrate the concept of 
// references 
class Rectangle 
{
  double length;
  double breadth;
}

class RectangleDemo
{
    public static void main(String args[])
    {

    // r1 is reference variable which contain 
    // the address of Actual Rectangle Object.
    Rectangle r1 = new Rectangle();

    // r2 is another reference variable
    // r2 is initialized with r1 means:
    // r1 and r2 both are referring same object 
    // thus it does not create duplicate object 
    // nor does it allocate extra memory.
    Rectangle r2 = r1;

    r1.length = 10;
    r2.length = 20;

    System.out.println("Value of R1's Length : " + r1.length);
    System.out.println("Value of R2's Length : " + r2.length);

    }
}
```

输出:

```java
Value of R1's Length : 20.0
Value of R2's Length : 20.0

```

**相关文章:**

*   [C/C++指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)
*   [Java 严格按值传递](https://www.geeksforgeeks.org/g-fact-31-java-is-strictly-pass-by-value/)

本文由 **Megha Bagri** 供稿。如果你喜欢 Geeksf[/source code]orgeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。