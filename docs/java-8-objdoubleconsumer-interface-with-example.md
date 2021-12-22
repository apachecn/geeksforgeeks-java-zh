# Java 8 | objddoubleconsumer 接口示例

> 原文:[https://www . geesforgeks . org/Java-8-objdoubleconsumer-interface-with-example/](https://www.geeksforgeeks.org/java-8-objdoubleconsumer-interface-with-example/)

**ObjDoubleConsumer 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受两个参数并产生一个结果的函数。然而，这类函数不返回值。

因此，这个功能接口采用一个通用的，即:-

*   **T** :表示操作的输入参数的类型

分配给 ObjDoubleConsumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终对其参数应用给定的操作。它接受一个双值和一个 T 值的参数，并且预期运行时没有任何副作用。这更像是使用类型为[双消费](https://www.geeksforgeeks.org/java-8-biconsumer-interface-in-java-with-examples/) < T，双>的对象，除了在这种情况下一个是引用，一个是原始数据类型。因此，当调用这个函数时，我们将获得一个引用和一个值。

### ObjDoubleConsumer 接口中的函数

ObjDoubleConsumer 接口由以下两个功能组成:

### 1.接受()

此方法接受两个值，并对给定的参数执行操作。

**语法:**

```java
void accept(T t, double value)
```

**参数:**该方法采用两个参数:

*   **t**–第一个输入参数
*   **值**–第二个输入参数

**返回值:**此方法不返回值。

下面是说明 accept()方法的代码:

**程序:**

```java
// Java code to demonstrate
// accept() method of ObjDoubleConsumer Interface

import java.util.Arrays;
import java.util.List;
import java.util.function.ObjDoubleConsumer;
import java.util.stream.Stream;

public class GFG {
    public static void main(String args[])
    {

        // Get the list from which
        // the Interface is to be instantiated.
        List<Integer>
            arr = Arrays.asList(3, 2, 5, 7, 4);

        // Instantiate the ObjDoubleConsumer interface
        ObjDoubleConsumer<List<Integer> >
            func = (list, num) ->
        {
            list.stream()
                .forEach(
                    a -> System.out.println(a * num));
        };
        func.accept(arr, 2.0);
    }
}
```

**Output:**

```java
6.0
4.0
10.0
14.0
8.0

```