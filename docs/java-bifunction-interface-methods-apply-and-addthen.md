# Java |双功能接口方法–apply()和 addThen()

> 原文:[https://www . geesforgeks . org/Java-bifunction-interface-methods-apply-and-addthen/](https://www.geeksforgeeks.org/java-bifunction-interface-methods-apply-and-addthen/)

**双功能接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[功能编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受两个参数并产生一个结果的函数。

因此，该功能接口采用 3 个参数，即

*   **T** :表示函数第一个参数的类型
*   **U** :表示函数第二个参数的类型
*   **R** :表示功能的返回类型

分配给双函数类型对象的 lambda 表达式用于定义其 **apply()** ，该表达式最终将给定函数应用于参数。使用双函数的主要优点是，它允许我们使用 2 个输入参数，而在函数中，我们只能有 1 个输入参数。

### 双功能界面中的功能

双功能界面由以下两个功能组成:

##### 1.应用()

此方法将给定的函数应用于参数。

**语法:**

```
R apply(T t, U u)
```

**参数:**该方法取两个参数:

*   **t**–第一个函数参数
*   **u**–第二个函数参数

**返回:**该方法返回 r 类型的函数结果

下面是说明 apply()方法的代码:

**程序 1:**

```
// Java Program to demonstrate
// BiFunction's apply() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction to add 2 numbers
        BiFunction<Integer, Integer, Integer> add = (a, b) -> a + b;

        // Implement add using apply()
        System.out.println("Sum = " + add.apply(2, 3));

        // BiFunction to multiply 2 numbers
        BiFunction<Integer, Integer, Integer> multiply = (a, b) -> a * b;

        // Implement add using apply()
        System.out.println("Product = " + multiply.apply(2, 3));
    }
}
```

**Output:**

```
Sum = 5
Product = 6

```

##### 2.添加然后()

它返回一个组合函数，其中参数化函数将在第一个函数之后执行。如果对任一函数的计算引发错误，它将被传递给组合函数的调用方。

**注意:**作为参数传递的函数应该是 function 类型，而不是 BiFunction 类型。

**语法:**

```
default <V> 
    BiFunction<T, U, V> 
        andThen(Function<? super R, ? extends V> after)
```

其中 **V** 是 after 函数和组合函数的输出类型

**参数:**该方法在后接受一个参数**，该参数是该函数为 1 后要应用的函数。**

**返回值:**该方法返回一个组合函数，首先应用当前函数，然后应用 after 函数

**异常:**如果 after 函数为空，该方法抛出 **NullPointerException** 。

下面是说明 addThen()方法的代码:

**程序 1:**

```
// Java Program to demonstrate
// BiFunction's addThen() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction to demonstrate composite functions
        // Here it will find the sum of two integers
        // and then return twice their sum
        BiFunction<Integer, Integer, Integer> composite1 = (a, b) -> a + b;

        // Using addThen() method
        composite1 = composite1.andThen(a -> 2 * a);

        // Printing the results
        System.out.println("Composite1 = " + composite1.apply(2, 3));

        // BiFunction to demonstrate composite functions
        // Here it will find the sum of two integers
        // and then return twice their sum
        BiFunction<Integer, Integer, Integer> composite2 = (a, b) -> a * b;

        // Using addThen() method
        composite2 = composite2.andThen(a -> 3 * a);

        // Printing the result
        System.out.println("Composite2 = " + composite2.apply(2, 3));
    }
}
```

**Output:**

```
Composite1 = 10
Composite2 = 18

```

**程序 2:** 演示何时返回 NullPointerException。

```
// Java Program to demonstrate
// BiFunction's addThen() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction which finds the sum of 2 integers
        // and returns twice their sum
        BiFunction<Integer, Integer, Integer> composite = (a, b) -> a + b;

        try {
            // Using addThen() method
            composite = composite.andThen(null);

            // Printing the result
            System.out.println("Composite = " + composite.apply(2, 3));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.NullPointerException

```

**程序 3:** 演示 after 函数中的异常是如何返回和处理的。

在下面的程序中，当(2，3)作为参数传递给第一个函数时，它返回 sum 5。现在这个和将作为参数传递给 after 函数，即 addThen()方法。这里，将 5 传递给 after 函数会产生(5–5 = 0)，即分母将变为 0。因此将引发算术异常。这个异常将在 apply()函数中处理，而不是 addThen()函数。

```
// Java Program to demonstrate
// BiFunction's addThen() method

import java.util.function.BiFunction;

public class Main {
    public static void main(String args[])
    {
        // BiFunction which finds the sum of 2 integers
        // and returns twice their sum
        BiFunction<Integer, Integer, Integer> composite = (a, b) -> a + b;

        // Using addThen() method
        composite = composite.andThen(a -> a / (a - 5));

        try {
            // Printing the result using apply()
            System.out.println("Composite = " + composite.apply(2, 3));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.ArithmeticException: / by zero

```

**注:**

*   不可能使用 addThen()向现有的双功能添加双功能。
*   双功能接口在需要传递 2 个参数时很有用，不像功能接口只允许传递一个参数。但是，可以级联两个或多个函数对象来形成双函数，但在这种情况下，不可能同时使用这两个参数。这就是双功能的效用。
*   Lambda 表达式被用来初始化 BiFunction 接口中的 apply()方法。