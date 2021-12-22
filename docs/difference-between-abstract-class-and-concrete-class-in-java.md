# Java 中抽象类和具体类的区别

> 原文:[https://www . geesforgeks . org/Java 中抽象类和具体类的区别/](https://www.geeksforgeeks.org/difference-between-abstract-class-and-concrete-class-in-java/)

**[抽象类](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/) :** 抽象类是 Java 中由抽象关键字声明的一种类。抽象类不能直接实例化，即不能使用 new 关键字直接创建该类的对象。抽象类可以通过一个具体的子类来实例化，也可以通过定义所有的抽象方法和新语句来实例化。它可能包含也可能不包含抽象方法。抽象方法由抽象关键字声明，这样的方法不能有主体。如果一个类包含一个抽象方法，那么它也需要是抽象的。

**混凝土类:**Java 中的混凝土类是子类的一种类型，它实现了它所扩展到的超抽象类的所有抽象方法。它也有它实现的接口的所有方法的实现。

**抽象类 vs 具体类**

1.  **修饰符:**使用抽象修饰符声明抽象类。具体的类不应该用抽象关键字来声明，这样做的话，它也会变成一个抽象类。
2.  **实例化:**抽象类不能直接实例化，即不能使用 new 关键字直接创建该类的对象。抽象类可以通过一个具体的子类来实例化，也可以通过定义所有的抽象方法和新语句来实例化。可以使用新的关键字直接实例化具体的类。
    **示例:**抽象类的无效直接实例化。

```
abstract class DemoAbstractClass {
    abstract void display();
}

public class JavaApplication {
    public static void main(String[] args)
    {
        DemoAbstractClass AC = new DemoAbstractClass();
        System.out.println("Hello");
    }
}
```

**编译错误:**

```
prog.java:9: error: DemoAbstractClass is abstract; cannot be instantiated
        DemoAbstractClass AC = new DemoAbstractClass();
                               ^

```

**示例:**通过定义一个抽象类的所有抽象方法进行有效的实例化。

```
abstract class DemoAbstractClass {
    abstract void display();
}

public class JavaApplication {
    public static void main(String[] args)
    {
        DemoAbstractClass AC = new DemoAbstractClass() {
            void display()
            {
                System.out.println("Hi.");
            }
        };
        AC.display();
        System.out.println("How are you?");
    }
}
```

**Output:**

```
Hi.
How are you?

```

**示例:**使用 new 关键字直接实例化具体。

```
abstract class DemoAbstractClass {
    abstract void display();
}

class ConcreteClass extends DemoAbstractClass {
    void display()
    {
        System.out.println("Hi.");
    }
}

public class JavaApplication {
    public static void main(String[] args)
    {
        ConcreteClass C = new ConcreteClass();
        C.display();
        System.out.println("How are you?");
    }
}
```

**Output:**

```
Hi.
How are you?

```

*   **Abstract methods:** An abstract class may or may not, have an abstract method. A concrete class cannot have an abstract method, because class containing an abstract method must also be abstract.
    Let’s understand this by an example:-
    We have a class called “HttpServlet” in Servlet. Now, this class is special in its own way.
    **“HttpServlet is an abstract class, but it doesn’t contain any abstract methods”.**
    Let’s understand the meaning of the above statement in-depth:-
    -> HttpServlet is an abstract class because it doesn’t have proper implementation for its methods. Since it doesn’t have proper implementation for its methods, then what is the sense of creating objects for such class. Therefore, this class is made as abstract.

    **现在出现的问题是:-**
    **问:**如果方法没有得到适当的实现，那么为什么它们没有使它变得抽象？
    - >因为抽象方法是那些没有合适的主体定义的方法，所以我们在类中重写这些方法来给它一个合适的定义。所以基本上抽象的方法被用于压倒一切的目的。
    现在这个“httpersvlet”类包含 10 个方法，假设如果这些方法被抽象，那么我们需要覆盖“httpersvlet”类的所有 10 个方法，这是一个愚蠢的方法，因为我们只需要 doGet()和 doPost()方法。

    下面是一个用 Java 说明上述观点的示例程序:

    ```
    // Java program to show servlet example
    // Importing required Java libraries
    import java.io.*;
    import javax.servlet.*;
    import javax.servlet.http.*;

    // Extend HttpServlet class
    public class AdvanceJavaConcepts
        extends HttpServlet {
        private String output;

        // Initializing servelet
        public void init() throws ServletException
        {
            output = "Advance Java Concepts";
        }

        // Requesting and printing the output
        public void doGet(HttpServletRequest req,
                          HttpServletResponse resp)
            throws ServletException, IOException
        {
            resp.setContentType("text/html");
            PrintWriter out = resp.getWriter();
            out.println(output);
        }

        public void destroy()
        {
            System.out.println("Over");
        }
    }
    ```

    **输出:**

    ```
    Advance Java Concepts
    output
    Over

    ```

    **注意:**如前所述，HttpServlet 类不包含任何抽象方法。因此，程序可以成功运行，而不会覆盖它的所有方法。
    但是假设这个类包含所有抽象的方法，那么我们需要覆盖它的所有方法，尽管它们在我们的类中什么都不做。
    httpersvlet 类的方法原型有:

    1.  公共作废服务(ServletRequest，ServletResponse res)
    2.  受保护的 void 服务(HttpSerletRequest 请求，HttpServletResponse res)
    3.  protected void dogt(http serletrequest req，HttpServletResponse res)
    4.  protected void dopost(http serletrequest req，HttpServletResponse res)
    5.  protected void dohead(http serletrequest req，HttpServletResponse res)
    6.  protected void doooptions(http serletrequest req，HttpServletResponse res)
    7.  protected void doput(http serletrequest req，HttpServletResponse res)
    8.  protected void dotrace(http serletrequest req，HttpServletResponse res)
    9.  protected void doelete(http serletrequest req，HttpServletResponse res)
    10.  受保护的 void GetLastModified(HttpSerRequest 请求)

    如果我们的类是抽象的，那么这种方法的不必要的重写就会存在。

    **注:**然而在 NetBeans 等最新 IDE 中，它会通过给抽象方法一个空白体来自动覆盖所有抽象方法，减少了程序员要覆盖的头疼。

    *   **Final:** 抽象类不能是 **final** ，因为它的所有抽象方法都必须在子类中定义。一个具体的班级可以被宣布为**决赛**。*   **Interface:** An abstract class cannot implement an interface alone but it can implement an interface, by the use of a child class and not providing implementations of all of the interface’s methods. It is the responsibility of the first concrete class that has that abstract class as an ancestor to implement all of the methods in the interface.

    | 抽象类 | 混凝土类 |
    | --- | --- |
    | 抽象类是使用抽象修饰符声明的。 | 具体类是用抽象修饰符声明的。 |
    | 不能使用 new 关键字直接实例化抽象类。 | 可以使用 new 关键字直接实例化具体的类。 |
    | 抽象类可以包含也可以不包含抽象方法。 | 具体类不能包含抽象方法。 |
    | 抽象类不能声明为最终类。 | 一个具体的类可以被声明为最终类。 |
    | 通过不提供接口的所有方法的实现，实现接口是可能的。为此，需要一个子类.. | 接口中所有方法的简单实现。 |

    **一些要点:**

    *   具体类是抽象类的子类，它实现了它所有的抽象方法。
    *   抽象方法不能有主体。
    *   抽象类可以像其他类一样有静态字段和静态方法。
    *   抽象类不能声明为最终类。
    *   只有抽象类可以有抽象方法。
    *   私有的、最终的静态方法不能是抽象的，因为它不能在子类中被覆盖。
    *   抽象类不能有抽象构造函数。
    *   抽象类不能有抽象静态方法。
    *   如果一个类扩展了一个抽象类，那么它应该定义基础抽象类的所有抽象方法(覆盖)。如果没有，子类(扩展抽象类的类)也必须被定义为抽象类。