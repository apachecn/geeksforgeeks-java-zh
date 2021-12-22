# Java 中的比较器反转()方法，带示例

> 原文:[https://www . geesforgeks . org/comparator-reversed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/comparator-reversed-method-in-java-with-examples/)

Java 中[比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)的 **reversed()** 方法返回一个比较器，该比较器强制该比较器的逆序。如果您使用数组的排序方法，并在应用相反的方法后传递此比较器，那么它将按相反的顺序对数组进行排序。

**语法:**

```
default Comparator<T> reversed()
```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个比较器，该比较器强制该比较器反向排序。

下面的程序说明了反向()方法:

**程序一:**

## Java

```
// Java program to demonstrate
// Comparator.reversed()  method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        String[] Arraystrings = { "aman", "amar", "avik" };

        System.out.println("before sort : "
                           + Arrays.toString(Arraystrings));

        Comparator<String> comp = (String::compareTo);
        Arrays.sort(Arraystrings, comp.reversed());

        System.out.println("after sort : "
                           + Arrays.toString(Arraystrings));
    }
}
```

**输出**

```
before sort : [aman, amar, avik]
after sort : [avik, amar, aman]

```

**程序二:**

## Java

```
// Java program to demonstrate
// Comparator.reversed()  method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        String[] list = { "KKR", "CSK", "MI", "KXIP",
                          "RCB", "SRH", "DC", "RR" };

        System.out.println("Before sorting:");
        System.out.println(Arrays.toString(list));

        Comparator<String> comp = (String::compareTo);

        Arrays.sort(list, comp.reversed());

        System.out.println("After sorting:");
        System.out.println(Arrays.toString(list));
    }
}
```

**输出**

```
Before sorting:
[KKR, CSK, MI, KXIP, RCB, SRH, DC, RR]
After sorting:
[SRH, RR, RCB, MI, KXIP, KKR, DC, CSK]

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/comparator . html # reversed()](https://docs.oracle.com/javase/10/docs/api/java/util/Comparator.html#reversed())