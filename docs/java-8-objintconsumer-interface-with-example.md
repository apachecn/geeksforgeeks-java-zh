# Java 8 | ObjIntConsumer 接口示例

> 原文:[https://www . geesforgeks . org/Java-8-objintconsumer-interface-with-example/](https://www.geeksforgeeks.org/java-8-objintconsumer-interface-with-example/)

**ObjIntConsumer 接口**是 **java.util.function** 包的一部分，该包是从 java 8 开始引入的，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受两个参数并产生一个结果的函数。然而，这类函数不返回值。

因此，这个功能接口采用一个通用的，即:-

*   **T** :表示操作的输入参数的类型

分配给 ObjIntConsumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终对其参数应用给定的操作。它接受一个整型值和一个 T 型值的参数，并且可以在没有任何副作用的情况下运行。这更像是使用类型为[双消费者](https://www.geeksforgeeks.org/java-8-biconsumer-interface-in-java-with-examples/) < T，Int >的对象，除了在这种情况下一个是引用，一个是原始数据类型。因此，当调用这个函数时，我们将获得一个引用和一个值。

### 对象消费者界面中的功能

ObjIntConsumer 界面由以下两个功能组成:

### 1.接受()

此方法接受两个值，并对给定的参数执行操作。

**语法:**

```java
void accept(T t, int value)
```

**参数:**该方法采用两个参数:

*   **t**–第一个输入参数
*   **值**–第二个输入参数

**返回值:**此方法不返回值。

下面是说明 accept()方法的代码:

**程序:**

```java
// Java code to demonstrate
// accept() method of ObjIntConsumer Interface

import java.util.Arrays;
import java.util.List;
import java.util.function.ObjIntConsumer;
import java.util.stream.Stream;

public class GFG {
    public static void main(String args[])
    {

        // Get the list from which
        // the Interface is to be instantiated.
        List<Integer>
            arr = Arrays.asList(3, 2, 5, 7, 4);

        // Instantiate the ObjIntConsumer interface
        ObjIntConsumer<List<Integer> >
            func = (list, num) ->
        {
            list.stream()
                .forEach(
                    a -> System.out.println(a * num));
        };
        func.accept(arr, 2);
    }
}
```

**Output:**

```java
6
4
10
14
8

```