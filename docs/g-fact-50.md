# Java 中的默认构造函数

> 原文:[https://www.geeksforgeeks.org/g-fact-50/](https://www.geeksforgeeks.org/g-fact-50/)

和 C++一样，Java [在没有用户](https://www.geeksforgeeks.org/g-fact-26/)编写的默认或参数化构造函数的情况下，会自动创建默认构造函数，(和 C++一样)默认构造函数会自动调用父默认构造函数。但与 C++不同，Java 中的默认构造函数将成员数据变量初始化为默认值(数值初始化为 0，布尔值初始化为*假*，引用初始化为*空*)。

例如，以下程序的输出为

0
null
false
0
0.0

```
// Main.java
class Test {
   int i;
   Test t;
   boolean b;
   byte bt;
   float ft;
}

public class Main {
    public static void main(String args[]) {
      Test t = new Test(); // default constructor is called.
      System.out.println(t.i);
      System.out.println(t.t);
      System.out.println(t.b);
      System.out.println(t.bt);
      System.out.println(t.ft);
    }
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。

参考文献:
[http://LEEP . net/notes-Java/OOP/constructors/constructor . html](http://leepoint.net/notes-java/oop/constructors/constructor.html)