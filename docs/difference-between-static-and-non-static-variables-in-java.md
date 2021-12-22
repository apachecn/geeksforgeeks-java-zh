# Java 中静态变量和非静态变量的区别

> 原文:[https://www . geesforgeks . org/Java 中静态变量和非静态变量的区别/](https://www.geeksforgeeks.org/difference-between-static-and-non-static-variables-in-java/)

Java 中有三种类型的[变量:](https://www.geeksforgeeks.org/variables-in-java/)

*   局部变量
*   实例变量
*   静态变量

局部变量和实例变量合称为非静态变量。因此，也可以说 Java 变量可以分为两类:

*   **Static Variables:** When a variable is declared as static, then a single copy of the variable is created and shared among all objects at a class level. Static variables are, essentially, global variables. All instances of the class share the same static variable.

    **静态变量的要点:-**

    *   我们只能在类级别创建静态变量。见这里
    *   静态块和静态变量按照它们在程序中出现的顺序执行。

    下面是 Java 程序，演示了静态块和静态变量是按照它们在程序中出现的顺序执行的。

    ```
    // Java program to demonstrate execution
    // of static blocks and variables
    class Test {
        // static variable
        static int a = m1();

        // static block
        static
        {
            System.out.println("Inside static block");
        }

        // static method
        static int m1()
        {
            System.out.println("from m1");
            return 20;
        }

        // static method(main !!)
        public static void main(String[] args)
        {
            System.out.println("Value of a : " + a);
            System.out.println("from main");
        }
    }
    ```

    **输出:**

    ```
    from m1
    Inside static block
    Value of a : 20
    from main

    ```

*   **Non-Static Variable**
    *   **局部变量**:在块、方法或构造函数中定义的变量称为局部变量。
        *   这些变量是在进入程序块或函数在退出程序块后被调用和销毁时，或函数调用返回时创建的。
        *   这些变量的作用域只存在于声明该变量的块中。也就是说，我们只能在该块内访问这些变量。
        *   局部变量的初始化是强制性的。
    *   **实例变量:**实例变量是非静态变量，在任何方法、构造函数或块之外的类中声明。
        *   由于实例变量是在类中声明的，因此这些变量是在类的对象创建时创建的，而在对象销毁时销毁。
        *   与局部变量不同，我们可以对实例变量使用访问说明符。如果我们没有指定任何访问说明符，那么将使用默认的访问说明符。
        *   实例变量的初始化不是强制性的。它的默认值是 0
        *   实例变量只能通过创建对象来访问。

    **示例:**

    ```
    // Java program to demonstrate
    // non-static variables

    class GfG {

        // non-static variable
        int rk = 10;

        public static void main(String[] args)
        {
            // Instance created inorder to access
            // a non static variable.
            Gfg f = new Gfg();

            System.out.println("Non static variable"
                               + " accessed using instance"
                               + " of a class");
            System.out.println("Non Static variable "
                               + f.rk);
        }
    }
    ```

    **Output:**

    ```
    Non static variable accessed using instance of a class.
    Non Static variable 10

    ```

**静态变量和非静态变量的主要区别是:**

| 静态变量 | 非静态变量 |
| --- | --- |
| 静态变量可以使用类名来访问 | 使用类的实例可以访问非静态变量 |
| 静态变量可以通过静态和非静态方法来访问 | 静态方法中不能访问非静态变量。 |
| 静态变量减少了程序使用的内存量。 | 非静态变量不会减少程序使用的内存量 |
| 静态变量在类的所有实例之间共享。 | 非静态变量特定于类的那个实例。 |
| 静态变量就像一个全局变量，所有方法都可以使用。 | 非静态变量就像一个局部变量，只能通过一个类的实例来访问。 |