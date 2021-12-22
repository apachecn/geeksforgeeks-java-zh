# Java 允许静态局部变量吗？

> 原文:[https://www.geeksforgeeks.org/g-fact-47/](https://www.geeksforgeeks.org/g-fact-47/)

与 C/C++不同，Java 中不允许静态局部变量。比如下面的 Java 程序编译失败，错误*“不允许静态局部变量”*

```java
class Test {
   public static void main(String args[]) { 
     System.out.println(fun());
   }

   static int fun()
   {
     static int x= 10;  //Error: Static local variables are not allowed
     return x--;
   }
} 
```

在 Java 中，静态变量是类变量(对于整个类)。所以如果我们有静态局部变量(作用域限于函数的变量)，就违背了静态的目的。因此编译器不允许静态局部变量。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。