# Java 中的继承和构造函数

> 原文:[https://www.geeksforgeeks.org/g-fact-67/](https://www.geeksforgeeks.org/g-fact-67/)

在 Java 中，没有参数的基类构造函数在派生类构造函数中被自动调用。例如，以下程序的输出为:
*基类构造函数调用*
*派生类构造函数调用*

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// filename: Main.java
class Base {
  Base() {
    System.out.println("Base Class Constructor Called ");
  }
}

class Derived extends Base {
  Derived() {
    System.out.println("Derived Class Constructor Called ");
  }
}

public class Main {
  public static void main(String[] args) { 
    Derived d = new Derived();
  }
}
```

但是，如果我们想调用基类的参数化构造函数，那么我们可以使用 super()调用它。需要注意的是**基类构造函数调用必须是派生类构造函数**中的第一行。例如，在下面的程序中，super(_x)是第一行派生类构造函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// filename: Main.java
class Base {
  int x;
  Base(int _x) {
    x = _x;
  }
}

class Derived extends Base {
  int y;
  Derived(int _x, int _y) {
    super(_x);
    y = _y;
  }
  void Display() {
    System.out.println("x = "+x+", y = "+y);
  }
}

public class Main {
  public static void main(String[] args) { 
    Derived d = new Derived(10, 20);
    d.Display();
  }
}
```

输出:
*x = 10，y = 20*
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息。