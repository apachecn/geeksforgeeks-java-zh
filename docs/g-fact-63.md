# Java 中静态函数的阴影

> 原文:[https://www.geeksforgeeks.org/g-fact-63/](https://www.geeksforgeeks.org/g-fact-63/)

在 Java 中，如果派生类静态函数的名称与基类静态函数的名称相同，那么基类静态函数会隐藏派生类静态函数。例如，下面的 Java 代码打印了*“a . fun()”*
注意:静态方法是一个类属性，所以如果从类名或具有类容器的对象调用静态方法，那么调用该类的方法不是对象的方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// file name: Main.java

// Parent class
class A {
    static void fun() { System.out.println("A.fun()"); }
}

// B is inheriting A
// Child class
class B extends A {
    static void fun() { System.out.println("B.fun()"); }
}

// Driver Method
public class Main {
    public static void main(String args[])
    {
        A a = new B();
        a.fun(); // prints A.fun();

        // B a = new B();
        // a.fun(); // prints B.fun()

        // the variable type decides the method
        // being invoked, not the assigned object type
    }
}
```

**Output**

```
A.fun()

```

**注意:**如果我们将 A.fun()和 B.fun()都设为非静态，那么上面的程序将打印“B.fun()”。虽然这两种方法都是静态类型，但是变量类型决定被调用的方法，而不是被分配的对象类型
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。