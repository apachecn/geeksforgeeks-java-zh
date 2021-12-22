# Java 整数缓存

> 原文:[https://www.geeksforgeeks.org/java-integer-cache/](https://www.geeksforgeeks.org/java-integer-cache/)

**先决条件:**[Java 内部类](https://www.geeksforgeeks.org/inner-class-java/#:~:text=Inner%20class%20means%20one%20class,of%20inner%20classes%20in%20java.&text=Nested%20Inner%20class%20can%20access,protected%2C%20public%20and%20default%20modifier.)|[Java 中的原始数据类型](https://www.geeksforgeeks.org/data-types-in-java/#:~:text=Java%20has%20two%20categories%20of,as%20String%2C%20Array%2C%20etc.)|[Java 中的自动装箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)

Java 不仅是一种语言，更是一种技术。Java 有明确定义的标准。在本文中，我们将讨论整数缓存。这个特性是在 Java 5 中引入的，目的是改善内存管理。让我们首先看一下示例代码，以更好地理解这种行为。之后，我们将讨论为什么要实现这一点。

在下面给出的程序中，您将清楚地理解逻辑，并看到如何初始化变量 a 和 b，以及 Java 如何在整数缓存中保存变量值。之后，您将看到-128 到 127 范围内的实例。此整数缓存仅在自动装箱时有效，这意味着从基元类型到对象引用的转换称为自动装箱。

让我们考虑下面给出的 java 代码输出示例:

**<u>例:</u>**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

class GFG {

    public static void main(String[] args)
    {

        // Initializing variable a and b.
        // Java keeps a integer cache of integer
        // instances in range of -128 to 127.
        // Integer Cache works only on autoboxing.
        // Conversion from primitive type to object
        // reference is called autoboxing.

        // In range declaration (-128 to 127) then
        // object reference will be same.
        Integer a = 9;
        Integer b = 9;

        // Then it will be true because both value of
        // a and b will point to the same object reference.
        if (a == b)
        {
            System.out.println("a==b");
        }
        else {
            System.out.println("a!=b");
        }

        // Not in range declaration (-128 to 127) then
        // then object reference will not be same in this
        // case.
        Integer x = 396;
        Integer y = 396;

        // Then it will be false because both value of
        // a and b will point to the different different
        // memory location.
        if (x == y) {
            System.out.println("x==y");
        }
        else
        {
          System.out.println("x!=y");
        }
    }
}
```

**输出:**

```
a==b
x!=y
```

在这里，我们预期如果条件部分，两者都应该运行。因为我们都知道在 java 中== compare reference 和 equals()比较数据。但在这种情况下，行为并不像预期的那样。我们已经看到了意想不到的产出。

**<u>Java 整数缓存实现:</u>**

在 Java 5 中，引入了一个新特性来节省内存并提高整数类型对象处理的性能。整数对象在内部缓存，并通过相同的引用对象重用。

*   这适用于–128 到+127 范围内的整数值。
*   这种整数缓存只在自动装箱时有效。当使用构造函数生成整数对象时，它们不会被缓存。

**汽车兴:**

这相当于按如下方式使用()的值:

```
Integer a=10; // this is autoboxing
Integer b==new Integer(40); // under the hood
```

**英特尔高速缓存类:**

IntegerCache 是一个私有的、静态的和内部的 Java 类。由于 Java 维护标准，这也被很好地记录下来，并给出了完整的信息。下面给出了英特尔高速缓存的内部实现。现在，您将在 java 中看到 IntegerCache 的内部实现逻辑。

在下面给定的程序中，var0、var1、var2、var3 和高表示检查英特尔高速缓存值的范围，通过检查，您还可以看到英特尔高速缓存的范围值，因此该类用于-128 到 127 之间的值的高速缓存。

它将帮助您检查任何对象引用值。如果值在范围声明中，那么两个值的对象引用将是相同的，如果它不在范围声明中，那么对象引用将是不同的。所以，如果你将比较值，即使它是相同的，这可能是偶然的，你已经采取了超出范围的值，那么，在这种情况下，两个值，即使它将是相同的，但将返回假意味着它不相等，因为对于两个值，对象引用将是不同的。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A program demonstrate IntegerCache
// implementation in Java.

// This is how IntegerCache class works.
private static class IntegerCache {

     // Method and variable declaration.
    static final int low = -128;
    static final int high;
    static final Integer[] cache;
    private IntegerCache() {}

    static
    {
        // Range value from -128 to 127
        int var0 = 127;
        String var1 = VM.getSavedProperty(
            "java.lang.Integer.IntegerCache.high");
        int var2;

       // Check if var1 value is null or not.
        if (var1 != null) {

          // For exception case
           try {
                var2 = Integer.parseInt(var1);
                var2 = Math.max(var2, 127);
                var0 = Math.min(var2, 2147483518);
            }
            catch (NumberFormatException var4) {
            }
        }

        high = var0;

       // High range for IntegerCache
        cache = new Integer[high - -128 + 1];
        var2 = -128;

       // defining var3 values using loop.
        for (int var3 = 0; var3 < cache.length; ++var3) {
            cache[var3] = new Integer(var2++);
        }
        assert high >= 127;
    }
}
```

**以上互联网缓存类说明:**

*   代码清楚地表明，该类用于缓存-128 到 127 之间的值。可以通过使用参数-XX: AutoBoxCacheMax=size 来修改高值 127。

**特征:**

*   它为您提供了根据我们的应用程序用例调整性能的灵活性。
*   它为您提供了从–128 到 127 之间选择数字的特定范围。
*   整数缓存使您能够缓存其他对象，例如字节、短、长等。