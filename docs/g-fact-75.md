# 功能过载和返回类型

> 原文:[https://www.geeksforgeeks.org/g-fact-75/](https://www.geeksforgeeks.org/g-fact-75/)

在 C++和 Java 中，如果函数仅在返回类型上不同，则不能重载函数。

比如下面的程序 C++和 Java 程序编译失败。

**C++程序**

```java
#include<iostream>
int foo() { 
    return 10; 
}

char foo() {  // compiler error; new declaration of foo()
    return 'a'; 
}

int main()
{
    char x = foo();
    getchar();
    return 0;
}
```

**Java 程序**

```java
// filename Main.java
public class Main {
    public int foo() {
        return 10;
    }
    public char foo() { // compiler error: foo() is already defined
        return 'a';
    }
    public static void main(String args[])
    { 
    }
}
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论