# Java 中的比较器 reverseOrder()方法，带示例

> 原文:[https://www . geesforgeks . org/comparator-reverse order-method-in-Java-with-examples/](https://www.geeksforgeeks.org/comparator-reverseorder-method-in-java-with-examples/)

Java 中[比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)的 **reverseOrder()** 方法返回一个比较器，用于以自然顺序的相反顺序比较可比对象。此方法返回的比较器是可序列化的，并且在比较 null 时引发 NullPointerException。

**语法:**

```
static <T extends Comparable<T>> 
    Comparator<T> reverseOrder()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个比较器，该比较器对可比对象进行反向自然排序。

下面的程序说明了 reverseOrder()方法:
**程序 1:**

```
// Java program to demonstrate
// Comparator.reverseOrder()  method

import java.util.Arrays;
import java.util.Comparator;
import java.util.List;

public class GFG {
    public static void main(String... args)
    {

        List<Integer> values
            = Arrays.asList(212, 324,
                            435, 566,
                            133, 100,
                            121);

        // reverseOrder is a static method
        values.sort(Comparator.reverseOrder());

        // print sorted number based on natural order
        System.out.println(values);
    }
}
```

打印在集成开发环境控制台上的输出如下所示。
**输出:**
![](img/0fcd4e82f02d8b79cbd566bf69c6736a.png)

**程序 2:**

```
// Java program to demonstrate
// Comparator.reverseOrder()  method

import java.util.Arrays;
import java.util.Comparator;
import java.util.List;

public class GFG {
    public static void main(String... args)
    {

        List<String> stringList
            = Arrays.asList("Aman", "Kajal",
                            "Joyita", "Das");

        System.out.println("Before sorting:");
        stringList.forEach(System.out::println);

        stringList.sort(Comparator.reverseOrder());
        System.out.println("\nAfter sorting:");
        stringList.forEach(System.out::println);
    }
}
```

控制台上打印的输出如下所示。
**输出:**
![](img/9822436c260ecc7658bf0049582a9cb9.png)

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/comparator . html # reverseOrder()](https://docs.oracle.com/javase/10/docs/api/java/util/Comparator.html#reverseOrder())