# Java . util . function . longbinaryooperator 接口示例

> 原文:[https://www . geesforgeks . org/Java-util-function-longbinaryooperator-interface-with-examples/](https://www.geeksforgeeks.org/java-util-function-longbinaryoperator-interface-with-examples/)

在 Java 8 中引入了**longbinaryooperator**接口。它表示对两个长值的操作，并将结果作为长值返回。这是一个[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此可以用作 lambda 表达式或方法引用。它主要用于需要从用户封装操作的时候。

**方法:**

1.  **【applyAsLong()】** : This function takes two long values, performs the required operation, and returns the long value.

    ```
    public long applyAsLong(long val1, long val2)

    ```

将 LongBinaryOperator 界面演示为[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)的示例。

```
// Java program to demonstrate LongBinaryOperator

import java.util.function.LongBinaryOperator;

public class LongBinaryOperatorDemo {
    public static void main(String[] args)
    {

        LongBinaryOperator longBinaryOperator = (x, y) ->
        {
            return x + y;
        };

        System.out.print("343666 + 547477 = ");
        System.out.println(longBinaryOperator
                               .applyAsLong(343666, 547477));

        LongBinaryOperator longBinaryOperator1 = (x, y) ->
        {
            return x * y;
        };
        System.out.print("343666 * 547477 = ");
        System.out.println(longBinaryOperator1
                               .applyAsLong(343666, 547477));
    }
}
```

**输出:**

```
343666 + 547477 = 891143
343666 * 547477 = 188149230682

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/function/longbinaryooperator . html](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongBinaryOperator.html)