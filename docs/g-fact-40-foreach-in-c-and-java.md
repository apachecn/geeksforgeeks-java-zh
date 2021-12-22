# c++和 Java 中的 Foreach

> 原文:[https://www . geesforgeks . org/g-fact-40-foreach-in-c-and-Java/](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/)

[Foreach 循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)用于快速访问数组的元素，无需执行初始化、测试和递增/递减。foreach 循环的工作是为每个元素做一些事情，而不是做 n 次。

C 语言中没有 foreach 循环，但是 C++和 Java 都支持 foreach 类型的循环。在 C++中，它是在 C++ 11 中引入的，在 JDK 1.5.0 中是在 Java 中引入的

foreach 循环使用的关键字在 C++和 Java 中都是“”的“**”。**

**C++程序:**

```java
// C++ program to demonstrate use of foreach
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 10, 20, 30, 40 };

    // Printing elements of an array using
    // foreach loop
    for (int x : arr)
        cout << x << endl;
}
```

**Output:**

```java
10
20
30
40

```

**Java 程序**

```java
// Java program to demonstrate use of foreach
public class Main {
    public static void main(String[] args)
    {
        // Declaring 1-D array with size 4
        int arr[] = { 10, 20, 30, 40 };

        // Printing elements of an array using
        // foreach loop
        for (int x : arr)
            System.out.println(x);
    }
}
```

**Output:**

```java
10
20
30
40

```

Foreach 循环的优点:-
1)使代码更易读。
2)消除编程错误的可能性。

本文由**拉胡尔·阿格沃尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论