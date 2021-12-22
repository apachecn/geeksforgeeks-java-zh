# 增量运算符和减量运算符的区别

> 原文:[https://www . geesforgeks . org/递增和递减运算符之间的差异/](https://www.geeksforgeeks.org/difference-between-increment-and-decrement-operators/)

[像 C/C++/Java 这样的编程语言](https://www.geeksforgeeks.org/introduction-to-programming-languages/)都有[递增和递减运算符](https://www.geeksforgeeks.org/operators-in-java/)。这些都是非常有用和常见的运算符。

1.  **Increment Operators:** The increment operator is used to increment the value of a variable in an expression. In the Pre-Increment, value is first incremented and then used inside the expression. Whereas in the Post-Increment, value is first used inside the expression and then incremented.

    **语法:**

    ```
    // PREFIX
    ++m

    // POSTFIX
    m++

    where m is a variable

    ```

    **示例:**

    ```
    #include <stdio.h>

    int increment(int a, int b)
    {
        a = 5;

        // POSTFIX
        b = a++;
        printf("%d", b);

        // PREFIX
        int c = ++b;
        printf("\n%d", c);
    }

    // Driver code
    int main()
    {
        int x, y;
        increment(x, y);

        return 0;
    }
    ```

2.  **Decrement Operators:** The decrement operator is used to decrement the value of a variable in an expression. In the Pre-Decrement, value is first decremented and then used inside the expression. Whereas in the Post-Decrement, value is first used inside the expression and then decremented.

    **语法:**

    ```
    // PREFIX
    --m

    // POSTFIX
    m--

    where m is a variable

    ```

    **示例:**

    ```
    #include <stdio.h>

    int decrement(int a, int b)
    {
        a = 5;

        // POSTFIX
        b = a--;
        printf("%d", b);

        // PREFIX
        int c = --b;
        printf("\n%d", c);
    }

    // Driver code
    int main()
    {
        int x, y;
        decrement(x, y);

        return 0;
    }
    ```

    **递增运算符和递减运算符的区别:**

    | 增量运算符 | 递减运算符 |
    | --- | --- |
    | 递增运算符将操作数加 1。 | 递减运算符从操作数中减去 1。 |
    | 后缀增量运算符意味着表达式首先使用变量的原始值进行计算，然后变量递增(增加)。 | 后缀递减运算符意味着首先使用变量的原始值计算表达式，然后变量递减(减少)。 |
    | 前缀递增运算符意味着首先递增变量，然后使用变量的新值计算表达式。 | 前缀递减运算符意味着首先递减变量，然后使用变量的新值计算表达式。 |
    | 通常，我们在决策和循环中使用这个。 | 这也用于决策和循环。 |