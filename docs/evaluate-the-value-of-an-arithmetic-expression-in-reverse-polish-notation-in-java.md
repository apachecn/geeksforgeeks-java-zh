# 用 Java 的逆波兰符号计算算术表达式的值

> 原文:[https://www . geesforgeks . org/evaluate-value-of-a-算术表达式-in-reverse-polish-in-Java 符号/](https://www.geeksforgeeks.org/evaluate-the-value-of-an-arithmetic-expression-in-reverse-polish-notation-in-java/)

**逆波兰符号**是后缀符号，用数学概念来表示操作数后面的运算符。让我们用一个问题陈述来实现 RPN

**问题陈述:**任务是使用像+、-、*、/这样的有效运算符找到数组中存在的算术表达式的值。每个操作数可以是整数或其他表达式。

**注意:**

1.  The dimension *partition between two integers should be truncated to zero.*
2.  *The given RPN expression is always valid. This means that the expression is always the result of calculation, and there will be no division by zero.*

图示为 RPN 的外行操作

```java
Input: ["2", "1", "+", "3", "*"]
Output: 9
Explanation: ((2 + 1) * 3) = 9

Input: ["4", "13", "5", "/", "+"]
Output: 6
Explanation: (4 + (13 / 5)) = 6

Input: ["10", "6", "9", "3", "+", "-11", "*", "/", "*", "17", "+", "5", "+"]
Output: 22
Explanation: 
  ((10 * (6 / ((9 + 3) * -11))) + 17) + 5
= ((10 * (6 / (12 * -11))) + 17) + 5
= ((10 * (6 / -132)) + 17) + 5
= ((10 * 0) + 17) + 5
= (0 + 17) + 5
= 17 + 5
= 22
```

**进场:**

解决这个问题的基本方法是使用**堆栈。**

*   Access all the elements in the array, and if the elements do not match the special characters ("+","-","*", "/"), push the elements onto the stack.
*   Then, whenever a special character is found, pop the first two elements from the stack and perform the operation, and then push the element into the stack again.
*   Repeat the above two processes for all elements in the array.
*   Finally, pop the element from the stack and print the result.

**实现:**

## 爪哇

```java
// Java Program to find the
// solution of the arithmetic
// using the stack
import java.io.*;
import java.util.*;

class solution {
    public int stacky(String[] tokens)
    {

        // Initialize the stack and the variable
        Stack<String> stack = new Stack<String>();
        int x, y;
        String result = "";
        int get = 0;
        String choice;
        int value = 0;
        String p = "";

        // Iterating to the each character
        // in the array of the string
        for (int i = 0; i < tokens.length; i++) {

            // If the character is not the special character
            // ('+', '-' ,'*' , '/')
            // then push the character to the stack
            if (tokens[i] != "+" && tokens[i] != "-"
                && tokens[i] != "*" && tokens[i] != "/") {
                stack.push(tokens[i]);
                continue;
            }
            else {
                // else if the character is the special
                // character then use the switch method to
                // perform the action
                choice = tokens[i];
            }

            // Switch-Case
            switch (choice) {
            case "+":

                // Performing the "+" operation by poping
                // put the first two character
                // and then again store back to the stack

                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = x + y;
                result = p + value;
                stack.push(result);
                break;

            case "-":

                // Performing the "-" operation by poping
                // put the first two character
                // and then again store back to the stack
                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = y - x;
                result = p + value;
                stack.push(result);
                break;

            case "*":

                // Performing the "*" operation
                // by poping put the first two character
                // and then again store back to the stack

                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = x * y;
                result = p + value;
                stack.push(result);
                break;

            case "/":

                // Performing the "/" operation by poping
                // put the first two character
                // and then again store back to the stack

                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = y / x;
                result = p + value;
                stack.push(result);
                break;

            default:
                continue;
            }
        }

        // Method to convert the String to integer
        return Integer.parseInt(stack.pop());
    }
}

class GFG {

    public static void main(String[] args)
    {
        // String Input
        String[] s
            = { "10", "6", "9",  "3", "+", "-11", "*",
                "/",  "*", "17", "+", "5", "+" };

        solution str = new solution();
        int result = str.stacky(s);
        System.out.println(result);
    }
}
```

**输出:**

```java
22
```

**时间复杂度:O(n)**