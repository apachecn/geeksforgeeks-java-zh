# Java 中的 Java . util . function . double predicate 接口，带示例

> 原文:[https://www . geesforgeks . org/Java-util-function-double predicate-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/java-util-function-doublepredicate-interface-in-java-with-examples/)

**双谓词**接口在 **JDK 8** 中引入。该接口封装在 **java.util.function** 包中。它对 Double 对象进行操作，并根据条件返回谓词值。这是一个[功能界面](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此也可以用于[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)。

```
public interface DoublePredicate
```

**方法**T2】

*   **test()** :该函数对双精度值进行条件检查，并返回一个表示结果的布尔值。

```
boolean test(double value)
```

*   **和()**:此函数对当前对象和作为参数接收的对象应用 and 运算，并返回新形成的谓词。此方法有默认实现。

```
default DoublePredicate and(DoublePredicate other)
```

*   **求反()**:此函数返回当前谓词的逆，即反转测试条件。此方法有默认实现。

```
default DoublePredicate negate()
```

*   **或()**:此函数对当前对象和作为参数接收的对象应用 or 运算，并返回新形成的谓词。此方法有默认实现。

```
default DoublePredicate or(DoublePredicate other)
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java example to demonstrate DoublePredicate interface

import java.util.function.DoublePredicate;

public class DoublePredicateDemo {
    public static void main(String[] args)
    {
        // DoublePredicate to check square
        // of x is less than 100
        DoublePredicate db
            = (x) -> { return x * x < 100.0; };
        System.out.println("100 is less than 100 "
                           + db.test(10));

        DoublePredicate db3;
        // Test condition reversed
        db.negate();
        System.out.println("100 is greater than 100 "
                           + db.test(10));

        DoublePredicate db2 = (x) ->
        {
            double y = x * x;
            return y >= 36 && y < 1000;
        };

        // Test condition ANDed
        // with another predicate
        db3 = db.and(db2);
        System.out.println("81 is less than 100 "
                           + db3.test(9));

        db3 = db.or(db2);
        // Test condition ORed with another predicate
        System.out.println("49 is greater than 36"
                           + " and less than 100 "
                           + db3.test(7));
    }
}
```

**Output:** 

```
100 is less than 100 false
100 is greater than 100 false
81 is less than 100 true
49 is greater than 36 and less than 100 true
```

**参考:**T2T4】