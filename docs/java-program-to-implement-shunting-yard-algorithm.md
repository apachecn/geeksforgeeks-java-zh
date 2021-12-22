# 实现调车场算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-调车场-算法/](https://www.geeksforgeeks.org/java-program-to-implement-shunting-yard-algorithm/)

调车场算法用于将中缀符号转换为反向波兰符号。后缀符号也称为逆波兰符号(RPN)。该算法被命名为“调车场”，因为它的活动类似于铁路调车场。这是一种表示表达式的方法，其中运算符符号放在被操作的参数之后。波兰符号**、**，其中运算符位于操作数之前。澳大利亚哲学家和计算机科学家建议将运算符放在操作数之后，因此创造了反向波兰符号。Dijkstra 开发了这个算法

**表示和解释:**

括号不需要表示术语的评估或分组顺序。RPN 表达式简单地从左到右计算，这大大简化了计算机程序中表达式的计算。举个例子，算术表达式。

从左到右解释可以执行以下两个执行

1.  如果该值出现在表达式的下一个位置，则将当前值推入堆栈。
2.  现在，如果操作符接下来出现，从堆栈中弹出最上面的两个元素，执行操作并将结果推回到堆栈中。

运算符的优先顺序是:

<figure class="table">

| 操作员 | 优先顺序 |
| --- | --- |
| ^ | three |
| / | Two |
| * | Two |
| +

 | one |
| – | one |

</figure>

**图解:** RPN 表达式会产生 2 和 3 的和，即 5:2 ^ 3+

> **输入:** (3+4)*5
> 
> **输出** : 3×4+5*
> 
> 这是上面中缀符号的后缀符号

**涉及的概念:**

<figure class="table">

| 栈的功能 | 在堆栈中执行的操作 |
| --- | --- |
| 推送() | 在堆栈中插入元素 |
| 流行音乐() | 从堆栈中移除当前最上面的元素 |
| peek() | 获取堆栈的顶部元素 |
| isEmpty() | 检查堆栈是否为空 |
| IsFull（） | 检查堆栈是否为空 |

</figure>

**示例:**

> **单数:a+b*(c^d-e)^(f+g*h)-i**
> 
> **邮政修正符号** : **abcd^e-fgh*+^*+i-**

**算法:** AE 是用中缀符号写的算术表达式，PE 将是 AE 的后缀表达式

1.  将“(”推到堆栈上，并添加“)”到 AE 的末尾。
2.  从左至右扫描声发射，对声发射的每个元素重复步骤 3 至 6，直到堆栈为空。
3.  如果遇到操作数，将其追加到 PE。
4.  如果遇到左括号，将其推到堆栈上。
5.  如果遇到一个运算符，那么:从堆栈中反复弹出，并向 PE 追加每个与该运算符具有相同或更高优先级的运算符。向堆栈添加运算符。[如果结束]
6.  如果遇到右括号，那么:从堆栈中反复弹出，并向每个操作符追加，直到遇到左括号。删除左括号。[如果结束][如果结束]
7.  g×h

对下面给出的两个例子应用相同的上述算法:

> **例 1 :** 在表达式“1 + 2”上应用调车场算法
> 
> 第一步:输入“1 + 2”
> 
> 步骤 2:将 1 推送到输出队列
> 
> 第三步:推+到操作符栈，因为+是操作符。
> 
> 步骤 4:将 2 推送到输出队列
> 
> 第五步:读取输入表达式后，输出队列和运算符堆栈弹出表达式，然后将它们添加到输出中。
> 
> 第六步:输出“1 2 +”

> **示例 2:** 在表达式 5 + 2 / (3- 8) ^ 5 ^ 2 上应用调车场算法
> 
> <figure class="table">
> 
> | 代币 | 行动 | 堆 | 输出 |
> | --- | --- | --- | --- |
> | five | “5”向输出添加令牌 |   | five |
> | + | 将令牌推送到堆栈 | + | five |
> | Two | “2”将令牌添加到输出 | + | 5 2 |
> | / | 将令牌推送到堆栈 | +/ | 5 2 |
> | （ | 将令牌推送到堆栈 | +/( | 5 2 |
> | three | “3”将令牌添加到输出 | +/( | 5 2 3 |
> | – | 将令牌推送到堆栈 | +/(- | 5 2 3 |
> | eight | “8”向输出添加令牌 | +/(- | 5 2 3 8 |
> | ) | 弹出堆栈到输出 | +/ | 5 2 3 8 – |
> | ^ | 将令牌推送到堆栈 | +/^ | 5 2 3 8 – |
> | five | “5”向输出添加令牌 | +/^ | 5 2 3 8 – 5 |
> | ^ | 将令牌推送到堆栈 | +/^ | 5 2 3 8 – 5^ |
> | Two | “2”将令牌添加到输出 | +/^ | 5 2 3 8 – 5 ^ 2 |
> | 结束 | 弹出整个堆栈 |   | 5238-5^2^/+ |
> 
> </figure>

**实施:**调车场算法

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Implemention of Shunting Yard Algorithm

// Importing stack class for stacks DS
import java.util.Stack;
// Importing specific character class as
// dealing with only operators and operands
import java.lang.Character;

class GFG {

    // Method is used to get the precedence of operators
    private static boolean letterOrDigit(char c)
    {
        // boolean check
        if (Character.isLetterOrDigit(c))
            return true;
        else
            return false;
    }

    // Operator having higher precedence
    // value will be returned
    static int getPrecedence(char ch)
    {

        if (ch == '+' || ch == '-')
            return 1;
        else if (ch == '*' || ch == '/')
            return 2;
        else if (ch == '^')
            return 3;
        else
            return -1;
    }

    // Method converts  given infixto postfix expression
    // to illustrate shunting yard algorithm
    static String infixToRpn(String expression)
    {
        // Initialising an empty String
        // (for output) and an empty stack
        Stack<Character> stack = new Stack<>();

        // Initially empty string taken
        String output = new String("");

        // Iterating ovet tokens using inbuilt
        // .length() function
        for (int i = 0; i < expression.length(); ++i) {
            // Finding character at 'i'th index
            char c = expression.charAt(i);

            // If the scanned Token is an
            // operand, add it to output
            if (letterOrDigit(c))
                output += c;

            // If the scanned Token is an '('
            // push it to the stack
            else if (c == '(')
                stack.push(c);

            // If the scanned Token is an ')' pop and append
            // it to output from the stack until an '(' is
            // encountered
            else if (c == ')') {
                while (!stack.isEmpty()
                       && stack.peek() != '(')
                    output += stack.pop();

                stack.pop();
            }

            // If an operator is encountered then taken the
            // further action based on the precedence of the
            // operator

            else {
                while (
                    !stack.isEmpty()
                    && getPrecedence(c)
                           <= getPrecedence(stack.peek())) {
                    // peek() inbuilt stack function to
                    // fetch the top element(token)

                    output += stack.pop();
                }
                stack.push(c);
            }
        }

        // pop all the remaining operators from
        // the stack and append them to output
        while (!stack.isEmpty()) {
            if (stack.peek() == '(')
                return "This expression is invalid";
            output += stack.pop();
        }
        return output;
    }

    // Main driver code
    public static void main(String[] args)
    {
        // Considering random infix string notation
        String expression = "5+2/(3-8)^5^2";

        // Printing RPN for the above infix notation
        // Illustrating shunting yard algorithm
        System.out.println(infixToRpn(expression));
    }
}
```

**Output**

```
5238-5^2^/+
```

*   **时间复杂度** : O(n)这个算法需要线性时间，因为我们只遍历表达式一次，pop 和 push 只取 O(1)。
*   **空间复杂度** : O(n)因为我们使用的是 n 大小的堆栈，其中 n 是给定表达式的长度。