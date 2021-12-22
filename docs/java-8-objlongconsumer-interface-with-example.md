# Java 8 | ObjLongConsumer 接口示例

> 原文:[https://www . geesforgeks . org/Java-8-objlongconsumer-interface-with-example/](https://www.geeksforgeeks.org/java-8-objlongconsumer-interface-with-example/)

**ObjLongConsumer Interface** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受两个参数并产生一个结果的函数。然而，这类函数不返回值。

因此，这个功能接口采用一个通用的，即:-

*   **T** :表示操作的输入参数的类型

分配给 ObjLongConsumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终对其参数应用给定的操作。它接受一个长值和一个 T 值参数，预计运行时不会有任何副作用。这更像是使用类型为双消费 T 龙 T5 的对象，除了在这种情况下一个是引用一个是原始数据类型。因此，当调用这个函数时，我们将获得一个引用和一个值。

### 对象消费者界面中的功能

ObjLongConsumer 界面由以下两个功能组成:

### 1.接受()

此方法接受两个值，并对给定的参数执行操作。

**语法:**

```
void accept(T t, long value)
```

**参数:**该方法采用两个参数:

*   **t**–第一个输入参数
*   **值**–第二个输入参数

**返回值:**此方法不返回值。

下面是说明 accept()方法的代码:

**程序:**

```
// Java code to demonstrate
// accept() method of ObjLongConsumer Interface

import java.util.Arrays;
import java.util.List;
import java.util.function.ObjLongConsumer;
import java.util.stream.Stream;

public class GFG {
    public static void main(String args[])
    {

        // Get the list from which
        // the Interface is to be instantiated.
        List<Integer>
            arr = Arrays.asList(3, 2, 5, 7, 4);

        // Instantiate the ObjLongConsumer interface
        ObjLongConsumer<List<Integer> >
            func = (list, num) ->
        {
            list.stream()
                .forEach(
                    a -> System.out.println(a * num));
        };
        func.accept(arr, 200000);
    }
}
```

**Output:**

```
600000
400000
1000000
1400000
800000

```