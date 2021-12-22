# Java 中只有+和*运算符的算术表达式

> 原文:[https://www . geesforgeks . org/算术表达式-java 中只有 and 运算符/](https://www.geeksforgeeks.org/arithmetic-expression-having-only-and-operators-in-java/)

在这里，我们将讨论包含加法和乘法等运算符的算术表达式，您将看到如何在程序的帮助下获取表达式并计算值。

给定一个只有+和*运算符的表达式，任务是计算字符串表达式并找到它的输出。在这里，它是一个简单的 java 程序来实现，其中表达式只包含加法(+)和乘法(*)运算符。

**例 1:**

```
Input: 1+2*3+4*5*6
Output: 127
Explanation: According to BODMAS, multiplication is evaluated 
             first giving an expression as: 1+6+120\. 
Finally the sum is 127.

```

**例 2:**

```
Input: 2*3*4
Output: 24

```

**例 3:**

这就是下面给出的 java 程序如何将字符串作为输入，并基于加法(+)和乘法(*)等运算符进行拆分。

```
1+2*3+4*5*6
|1|+|2*3|+|4*5|*6|
|1|+|6|+|20|*6
|1|+|6|+|120| = 127  

```

**进场:**

1.  用正则表达式匹配 **+** 符号分割字符串
2.  因此，结果字符串数组中的每个元素都有一个数字或一个乘积表达式。
3.  现在遍历数组，找到包含产品的索引。
4.  使用正则表达式匹配*号拆分产品表达式
5.  现在用第 4 步中的*号乘以每个被拆分的数字。
6.  最后，每个索引只有需要添加的数字，用于表达式的最终计算。
7.  在步骤 1 之后接收的数组中的所有索引处添加整数。
8.  求和给出了表达式字符串的最终结果。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

class GFG {

    static int calculator(String str)
    {
        // Split expression string using + operator.
        // Now every index will have either an integer or an
        // expression of only products.
        String[] arr = str.split("\\+");

        for (int i = 0; i < arr.length; i++) {
            int result = 1;

            // If index contains * sign,
            // split expression using *
            if (arr[i].contains("*")) {
                String[] num = arr[i].split("\\*");

                // Multiply each number separated by * and
                // store final product in 'result' variable
                for (int j = 0; j < num.length; j++) {
                    result *= Integer.parseInt(num[j]);
                }

                // Store resultant product value in the
                // array index. For ex: index having 2*3 is
                // replaced by 6 and index having 4*5*6 is
                // replaced by 120.
                arr[i] = String.valueOf(result);
            }
        }

        // Now every array index has a
        // single integer as element.
        int len = arr.length;
        int sum = 0;

        // Calculate the sum of all elements
        // of array to get final result.
        for (int i = 0; i < len; i++) {
            sum += Integer.parseInt(arr[i]);
        }

        // Return the final result
        return sum;
    }

    public static void main(String[] args)
    {
        // Expression string is: 1+2*3+4*5*6
        System.out.println(calculator("1+2*3+4*5*6"));
    }
}
```

**输出:**

```
127

```