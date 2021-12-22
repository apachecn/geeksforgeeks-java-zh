# Java 中类或接口的访问说明符

> 原文:[https://www . geesforgeks . org/access-Java 类或接口说明符/](https://www.geeksforgeeks.org/access-specifiers-for-classes-or-interfaces-in-java/)

在 Java 中，类/接口的方法和数据成员可以有以下四种访问说明符之一。访问说明符根据它们的限制顺序列出。

1)私有(在定义的类内可访问)
2)默认或包私有(未指定访问说明符时)
3)受保护的
4)公共(可从任何类访问)

但是，当在任何其他类之外声明时，类和接口本身只能有两个访问说明符。
1)公共
2)默认(未指定访问说明符时)

我们不能用私有或受保护的访问说明符声明类/接口。例如，以下程序编译失败。

```java
//filename: Main.java
protected class Test {}

public class Main {
  public static void main(String args[]) {

  }
}
```

注意:嵌套接口和类可以有所有的访问说明符。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。