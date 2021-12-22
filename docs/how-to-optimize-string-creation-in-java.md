# 如何在 Java 中优化字符串创建？

> 原文:[https://www . geesforgeks . org/如何在 java 中优化字符串创建/](https://www.geeksforgeeks.org/how-to-optimize-string-creation-in-java/)

***new***运算符通过为新对象动态分配(即运行时分配)内存并返回对该内存的引用来实例化一个类。该引用然后存储在变量中。 ***新的*** 运算符后面还跟一个对类构造函数的调用，该函数初始化新的对象。因为字符串创建是在 O(n)时间复杂度下最佳工作的过程，其中 n 是字符串的长度。

*执行时间可能根据计算机器的性能而变化。*

**例:**

```
String str = new String("GeeksforGeeks");
```

使用新的创建字符串所需的时间:

## 

```
// String creation using new keyword
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        // Array of string
        String str[] = new String[50000];

        // Clock starts
        long startTime = System.currentTimeMillis();

        for (int i = 0; i < 50000; i++) {
            // Create new String object and copy
            str[i] = new String("GeeksforGeeks");
        }

        // End Clock
        long endTime = System.currentTimeMillis();

        // Print Time
        System.out.println(
            "Creation time of String using 'new' keyword : "
            + (endTime - startTime) + " ms");
    }
}
```

**输出**

```
Creation time of String using 'new' keyword : 12 ms
```