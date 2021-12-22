# Java 中有没有等价于 C/C++的 typedef？

> 原文:[https://www . geeksforgeeks . org/Java 中有-有-任何-等效于-type def-of-c-c/](https://www.geeksforgeeks.org/is-there-any-equivalent-to-typedef-of-c-c-in-java/)

一句话，Java 里面没有**什么**相当于 C++的 **typedef** 。

在 Java 中，**类**用来命名和构造类型或者我们可以说**类**是 C++的**结构**和 **typedef** 的组合函数。但这是完全不同的事情，并不等同于任何地方的 **typedef** 。

**typedef:** 它是一个**关键字**而不是一个在 C/C++语言中用于为现有数据类型指定替代名称的函数。当使用 **typedef 关键字**时，数据类型的名称变得有点复杂时，它与用户定义的数据类型一起使用，除非没有必要。
**使用 typedef 的语法:**

```java
typedef existing_name alias_name;

```

## C++

```java
// C++ program to demonstrate typedef 
#include <bits/stdc++.h>
using namespace std;

// After this line BYTE can be used 
// in place of unsifted char 
typedef unsigned char BYTE; 

int main() 
{ 
    BYTE b1, b2; 
    b1 = 'a'; 
    cout << b1 ; 
    return 0; 
} 

// This code is contributed by shubhamsingh10
```

## C

```java
// C program to demonstrate typedef
#include <stdio.h>

// After this line BYTE can be used
// in place of unsifted char
typedef unsigned char BYTE;

int main()
{
    BYTE b1, b2;
    b1 = 'a';
    printf("%c ", b1);
    return 0;
}
```

**Output:**

```java
a

```