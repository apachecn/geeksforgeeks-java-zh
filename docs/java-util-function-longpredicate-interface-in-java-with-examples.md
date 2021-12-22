# Java 中的 Java . util . function . long 谓词接口，带示例

> 原文:[https://www . geesforgeks . org/Java-util-function-long predicate-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/java-util-function-longpredicate-interface-in-java-with-examples/)

**长谓词**接口在 **JDK 8** 中引入。该接口封装在 **java.util.function** 包中。它对长值进行操作，并根据条件返回谓词值。这是一个[功能界面](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此也可以用于[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)。

```
public interface LongPredicate
```

**方法**

*   **test()** :该函数对长值进行条件检查，并返回一个表示结果的布尔值。

```
boolean test(long value)
```

*   **和()**:此函数对当前对象和作为参数接收的对象应用 and 运算，并返回新形成的谓词。此方法有默认实现。

```
default LongPredicate and(LongPredicate other)
```

*   **求反()**:此函数返回当前谓词的逆，即反转测试条件。此方法有默认实现。

```
default LongPredicate negate()
```

*   **或()**:此函数对当前对象和作为参数接收的对象应用 or 运算，并返回新形成的谓词。此方法有默认实现。

```
default LongPredicate or(LongPredicate other)
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java example to demonstrate LongPredicate interface

import java.util.function.LongPredicate;

public class LongPredicateDemo {
    public static void main(String[] args)
    {
        // Predicate to check for equal to 500000
        LongPredicate longPredicate = (x) ->
        {
            return (x == 500000);
        };
        System.out.println("499999 is equal to 500000 "
                           + longPredicate.test(499999));

        // Predicate to check for less than equal to 500000
        LongPredicate longPredicate1 = (x) ->
        {
            return (x <= 500000);
        };
        System.out.println("499999 is less than equal to 500000 "
                           + longPredicate1.test(499999));

        // ANDing the two predicates
        LongPredicate longPredicate2
            = longPredicate.and(longPredicate1);
        System.out.println("500000 is equal to 500000 "
                           + longPredicate2.test(500000));

        // ORing the two predicates
        longPredicate2 = longPredicate.or(longPredicate1);
        System.out.println("500001 is less than equal to 500000 "
                           + longPredicate2.test(500001));

        // Negating the predicate
        longPredicate2 = longPredicate1.negate();
        System.out.println("499999 is greater than 500000 "
                           + longPredicate2.test(499999));
    }
}
```

**Output:** 

```
499999 is equal to 500000 false
499999 is less than equal to 500000 true
500000 is equal to 500000 true
500001 is less than equal to 500000 false
499999 is greater than 500000 false
```

**参考:**T2T4】