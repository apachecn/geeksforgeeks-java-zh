# Java 8 中的 Lambda 表达式

> 原文:[https://www.geeksforgeeks.org/lambda-expressions-java-8/](https://www.geeksforgeeks.org/lambda-expressions-java-8/)

Lambda 表达式基本表达[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)的实例(单一抽象方法的接口称为功能接口。一个例子是 java.lang.Runnable)。lambda 表达式只实现抽象函数，因此实现函数接口

lambda 表达式是在 Java 8 中添加的，并提供以下功能。

*   允许将功能视为方法参数，或将代码视为数据。
*   一种可以不属于任何类而创建的函数。
*   lambda 表达式可以像对象一样传递，并按需执行。

```
// Java program to demonstrate lambda expressions
// to implement a user defined functional interface.

// A sample functional interface (An interface with
// single abstract method
interface FuncInterface
{
    // An abstract function
    void abstractFun(int x);

    // A non-abstract (or default) function
    default void normalFun()
    {
       System.out.println("Hello");
    }
}

class Test
{
    public static void main(String args[])
    {
        // lambda expression to implement above
        // functional interface. This interface
        // by default implements abstractFun()
        FuncInterface fobj = (int x)->System.out.println(2*x);

        // This calls above lambda expression and prints 10.
        fobj.abstractFun(5);
    }
}
```

输出:

```
10
```

[![lambda expression](img/11d8d1514e58c5c490258fea0bb8927f.png)](https://media.geeksforgeeks.org/wp-content/uploads/lambda-expression.jpg) 
**语法:**

```
 lambda operator -> body
```

其中λ运算符可以是:

*   **零参数:**

    ```
    () -> System.out.println("Zero parameter lambda");
    ```

*   **One parameter:**–

    ```
    (p) -> System.out.println("One parameter: " + p);
    ```

    如果可以从上下文中推断出变量的类型，则不必使用括号

*   **多个参数:**

    ```
    (p1, p2) -> System.out.println("Multiple parameters: " + p1 + ", " + p2);
    ```

请注意:Lambda 表达式就像函数一样，它们接受参数就像函数一样。

```
// A Java program to demonstrate simple lambda expressions
import java.util.ArrayList;
class Test
{
    public static void main(String args[])
    {
        // Creating an ArrayList with elements
        // {1, 2, 3, 4}
        ArrayList<Integer> arrL = new ArrayList<Integer>();
        arrL.add(1);
        arrL.add(2);
        arrL.add(3);
        arrL.add(4);

        // Using lambda expression to print all elements
        // of arrL
        arrL.forEach(n -> System.out.println(n));

        // Using lambda expression to print even elements
        // of arrL
        arrL.forEach(n -> { if (n%2 == 0) System.out.println(n); });
    }
}
```

输出:

```
1
2
3
4
2
4
```

请注意，lambda 表达式只能用于实现函数接口。同样在上面的例子中，lambda 表达式实现了[消费者](https://docs.oracle.com/javase/8/docs/api/java/util/function/Consumer.html)功能接口。

一个用两个参数演示 lambda 表达式工作的 Java 程序。

```
// Java program to demonstrate working of lambda expressions
public class Test
{
    // operation is implemented using lambda expressions
    interface FuncInter1
    {
        int operation(int a, int b);
    }

    // sayMessage() is implemented using lambda expressions
    // above
    interface FuncInter2
    {
        void sayMessage(String message);
    }

    // Performs FuncInter1's operation on 'a' and 'b'
    private int operate(int a, int b, FuncInter1 fobj)
    {
        return fobj.operation(a, b);
    }

    public static void main(String args[])
    {
        // lambda expression for addition for two parameters
        // data type for x and y is optional.
        // This expression implements 'FuncInter1' interface
        FuncInter1 add = (int x, int y) -> x + y;

        // lambda expression multiplication for two parameters
        // This expression also implements 'FuncInter1' interface
        FuncInter1 multiply = (int x, int y) -> x * y;

        // Creating an object of Test to call operate using
        // different implementations using lambda Expressions
        Test tobj = new Test();

        // Add two numbers using lambda expression
        System.out.println("Addition is " +
                          tobj.operate(6, 3, add));

        // Multiply two numbers using lambda expression
        System.out.println("Multiplication is " +
                          tobj.operate(6, 3, multiply));

        // lambda expression for single parameter
        // This expression implements 'FuncInter2' interface
        FuncInter2 fobj = message ->System.out.println("Hello "
                                                 + message);
        fobj.sayMessage("Geek");
    }
}
```

输出:

```
Addition is 9
Multiplication is 18
Hello Geek

```

**重要点:**

*   lambda 表达式的主体可以包含零个、一个或多个语句。
*   当有单个语句时，花括号不是必需的，匿名函数的返回类型与 body 表达式的返回类型相同。
*   当有多个语句时，这些语句必须用花括号括起来(代码块)，匿名函数的返回类型与代码块中返回的值的类型相同，如果没有返回任何内容，则返回 void。

请看[这个](https://www.geeksforgeeks.org/sort-array-large-numbers/)。申请。

本文由**桑普达·考尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。