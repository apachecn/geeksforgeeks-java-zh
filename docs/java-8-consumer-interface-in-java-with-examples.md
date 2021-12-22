# Java 8 | Java 中的消费者界面，带示例

> 原文:[https://www . geesforgeks . org/Java-8-消费者-java 中的接口-示例/](https://www.geeksforgeeks.org/java-8-consumer-interface-in-java-with-examples/)

**消费者界面**是 **java.util.function** 包的一部分，该包是从 java 8 开始引入的，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受一个参数并产生一个结果的函数。然而，这类函数不返回值。
因此，该功能接口采用一个通用名称，即:-

*   **T** :表示操作的输入参数的类型

分配给 Consumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终对其参数应用给定的操作。当不需要返回任何价值时，消费者是有用的，因为他们被期望通过副作用来操作。

### 消费者界面中的功能

消费者界面由以下两个功能组成:

1.接受()

此方法接受一个值，并对给定的参数
**执行运算语法:**

```
void accept(T t)
```

**参数:**该方法取一个参数:

*   **t**–输入参数

**返回:**该方法不返回值。
下面是说明接受()方法的代码:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// Consumer's accept() method

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.function.Consumer;

public class Main {
    public static void main(String args[])
    {
        // Consumer to display a number
        Consumer<Integer> display = a -> System.out.println(a);

        // Implement display using accept()
        display.accept(10);

        // Consumer to multiply 2 to every integer of a list
        Consumer<List<Integer> > modify = list ->
        {
            for (int i = 0; i < list.size(); i++)
                list.set(i, 2 * list.get(i));
        };

        // Consumer to display a list of numbers
        Consumer<List<Integer> >
            dispList = list -> list.stream().forEach(a -> System.out.print(a + " "));

        List<Integer> list = new ArrayList<Integer>();
        list.add(2);
        list.add(1);
        list.add(3);

        // Implement modify using accept()
        modify.accept(list);

        // Implement dispList using accept()
        dispList.accept(list);
    }
}
```

**Output:** 

```
10
4 2 6
```

2.然后()

它返回一个组合消费者，其中参数化消费者将在第一个消费者之后执行。如果对任一函数的计算引发错误，它将被传递给组合操作的调用方。
**注意:**作为参数传递的函数应该是 Consumer 类型。
**语法:**

```
default Consumer <T> 
        andThen(Consumer<? super T> after)
```

**参数:**该方法接受之后的参数**，该参数是当前参数之后要应用的消费者。
**返回值:**该方法返回一个合成的 Consumer，该 Consumer 首先应用当前 Consumer，然后应用后操作。
**异常:**如果后操作为空，该方法抛出 **NullPointerException** 。
下面是代码说明，然后()方法:
**程序 1:**** 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// Consumer's andThen() method

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.function.Consumer;

public class Main {
    public static void main(String args[])
    {

        // Consumer to multiply 2 to every integer of a list
        Consumer<List<Integer> > modify = list ->
        {
            for (int i = 0; i < list.size(); i++)
                list.set(i, 2 * list.get(i));
        };

        // Consumer to display a list of integers
        Consumer<List<Integer> >
            dispList = list -> list.stream().forEach(a -> System.out.print(a + " "));

        List<Integer> list = new ArrayList<Integer>();
        list.add(2);
        list.add(1);
        list.add(3);

        // using addThen()
        modify.andThen(dispList).accept(list);
        ;
    }
}
```

**Output:** 

```
4 2 6
```

**程序 2:** 演示何时返回 NullPointerException。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// Consumer's andThen() method

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.function.Consumer;

public class Main {
    public static void main(String args[])
    {

        // Consumer to multiply 2 to every integer of a list
        Consumer<List<Integer> > modify = list ->
        {
            for (int i = 0; i < list.size(); i++)
                list.set(i, 2 * list.get(i));
        };

        // Consumer to display a list of integers
        Consumer<List<Integer> >
            dispList = list -> list.stream().forEach(a -> System.out.print(a + " "));

        List<Integer> list = new ArrayList<Integer>();
        list.add(2);
        list.add(1);
        list.add(3);
        try {
            // using addThen()
            modify.andThen(null).accept(list);
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

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// Consumer's andThen() method

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.function.Consumer;

public class Main {
    public static void main(String args[])
    {

        // Consumer to multiply 2 to every integer of a list
        Consumer<List<Integer> > modify = list ->
        {
            for (int i = 0; i <= list.size(); i++)
                list.set(i, 2 * list.get(i));
        };

        // Consumer to display a list of integers
        Consumer<List<Integer> >
            dispList = list -> list.stream().forEach(a -> System.out.print(a + " "));
        System.out.println();

        List<Integer> list = new ArrayList<Integer>();
        list.add(2);
        list.add(1);
        list.add(3);

        // using addThen()
        try {
            dispList.andThen(modify).accept(list);
            ;
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```
2 1 3 Exception: java.lang.IndexOutOfBoundsException: Index: 3, Size: 3
```