# Java 8 | Java 中的双用户界面，带示例

> 原文:[https://www . geesforgeks . org/Java-8-bicon sumer-in-Java-interface-with-examples/](https://www.geeksforgeeks.org/java-8-biconsumer-interface-in-java-with-examples/)

**双消费者接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受两个参数并产生一个结果的函数。然而，这类函数不返回值。

这个功能接口包含两个泛型，即

*   **T** :表示操作的第一个输入参数的类型
*   **U** :表示操作的第二个输入参数的类型

分配给双消费者类型对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终将给定的操作应用于其参数。

双消费者是有用的，当它不需要返回任何价值，因为他们预期通过副作用操作。

### 双用户界面中的功能

双用户界面由以下两个功能组成:

**1。accept()**

此方法接受两个值，并对给定的参数执行操作

**语法:**

```
void accept(T t, U u)
```

**参数:**该方法采用两个参数:

*   **t**–第一个输入参数
*   **u**–第二个输入参数

**返回:**该方法不返回值。

下面是说明 accept()方法的代码:

**程序 1:** 使用双消费者接受()方法比较 2 个整数列表的程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// BiConsumer's accept() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create the first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create the second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);
        listb.add(2);

        // BiConsumer to compare both lists
        BiConsumer<List<Integer>, List<Integer> >
            equals = (list1, list2) ->
        {
            if (list1.size() != list2.size()) {
                System.out.println("False");
            }
            else {
                for (int i = 0; i < list1.size(); i++)
                    if (list1.get(i) != list2.get(i)) {
                        System.out.println("False");
                        return;
                    }
                System.out.println("True");
            }
        };
        equals.accept(lista, listb);
    }
}
```

**Output:** 

```
False
```

**2。然后()**

它返回一个复合双消费者，其中参数化双消费者将在第一个双消费者之后执行。如果任一操作的计算引发错误，它将被中继到合成操作的调用方。

**注意:**作为参数传递的操作应为双消费者类型。

**语法:**

```
default BiConsumer <T, U> 
        andThen(BiConsumer<? super T, ? super U> after)
```

**参数:**该方法接受之后的参数**，该参数是当前参数之后要应用的双消费者。
**返回值:**该方法返回一个复合双消费者，首先应用当前操作，然后应用后操作。**

**异常:**如果后操作为空，该方法抛出**空指针异常**。

下面是说明 andThen()方法的代码:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// BiConsumer's andThen() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class Main {
    public static void main(String args[])
    {

        // Create first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);
        listb.add(2);

        // BiConsumer to compare 2 lists of integers
        BiConsumer<List<Integer>, List<Integer> > equals = (list1, list2) ->
        {
            if (list1.size() != list2.size()) {
                System.out.println("False");
            }
            else {
                for (int i = 0; i < list1.size(); i++)
                    if (list1.get(i) != list2.get(i)) {
                        System.out.println("False");
                        return;
                    }
                System.out.println("True");
            }
        };

        // BiConsumer to print 2 lists
        BiConsumer<List<Integer>, List<Integer> > disp = (list1, list2) ->
        {
            list1.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
            list2.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
        };

        // Using addThen() method
        equals.andThen(disp).accept(lista, listb);
    }
}
```

**Output:** 

```
False
2 1 3 
2 1 2
```

**程序 2:** 演示**空指针异常**何时返回。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// BiConsumer's andThen() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class Main {
    public static void main(String args[])
    {

        // Create first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);
        listb.add(2);

        // BiConsumer to compare 2 lists of integers
        BiConsumer<List<Integer>, List<Integer> > equals = (list1, list2) ->
        {
            if (list1.size() != list2.size()) {
                System.out.println("False");
            }
            else {
                for (int i = 0; i < list1.size(); i++)
                    if (list1.get(i) != list2.get(i)) {
                        System.out.println("False");
                        return;
                    }
                System.out.println("True");
            }
        };

        // BiConsumer to print 2 lists
        BiConsumer<List<Integer>, List<Integer> > disp = (list1, list2) ->
        {
            list1.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
            list2.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
        };

        try {
            equals.andThen(null).accept(lista, listb);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output**

```
Exception : java.lang.NullPointerException
```

**程序 3:** 演示函数返回后异常是如何处理的。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// BiConsumer's andThen() method

import java.util.ArrayList;
import java.util.List;
import java.util.function.BiConsumer;

public class Main {
    public static void main(String args[])
    {

        // Create first list
        List<Integer> lista = new ArrayList<Integer>();
        lista.add(2);
        lista.add(1);
        lista.add(3);

        // Create second list
        List<Integer> listb = new ArrayList<Integer>();
        listb.add(2);
        listb.add(1);

        // BiConsumer to compare 2 lists of integers
        BiConsumer<List<Integer>, List<Integer> > equals = (list1, list2) ->
        {
            for (int i = 0; i < list1.size(); i++)
                if (list1.get(i) != list2.get(i)) {
                    System.out.println("False");
                    return;
                }
            System.out.println("True");
        };

        // BiConsumer to print 2 lists
        BiConsumer<List<Integer>, List<Integer> > disp = (list1, list2) ->
        {
            list1.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
            list2.stream().forEach(a -> System.out.print(a + " "));
            System.out.println();
        };

        try {
            disp.andThen(equals).accept(lista, listb);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output**

```
2 1 3 
2 1 
Exception : java.lang.IndexOutOfBoundsException: Index 2 out of bounds for length 2
```