# Java 中的 BrainFuck 解释器

> 原文:[https://www.geeksforgeeks.org/brainfuck-interpreter-java/](https://www.geeksforgeeks.org/brainfuck-interpreter-java/)

Brainfuck 仅由八个简单的命令和一个指令指针组成。虽然它完全是图灵完整的，但它并不是为了实际应用，而是为了挑战和娱乐程序员。
智能操仅由 8 个字符命令组成，这使得它的使用非常具有挑战性，即使是简单的任务–

*   >命令递增数据指针(指向右边的下一个单元格)。

*   +命令递增(增加一)数据指针处的字节。
*   –命令使数据指针处的字节递减(减少 1)。
*   那个。命令输出数据指针处的字节。
*   命令接受一个字节的输入，将其值存储在数据指针所在的字节中。
*   [–如果数据指针处的字节为零，则不要将指令指针向前移动到下一个命令，而是将其向前跳转到匹配命令之后的命令]。
*   ]–如果数据指针处的字节是非零的，那么不要将指令指针向前移动到下一个命令，而是将其跳回到匹配的[命令]之后的命令。
*   (或者，]命令可以被翻译为无条件跳转到相应的[命令，反之亦然；由于不必要的重复搜索，程序将表现相同，但运行更慢。)
*   [ and ]匹配就像括号通常做的那样:每个[恰好匹配一个]，反之亦然，则[排在第一位，两者之间不能有不匹配的[ or ]。

由于 brainHock 只包含这 8 个命令，因此为 brainHock 构建解释器非常简单。在本文中，我们将构建一个简单的程序，该程序以一个 BrainFuck 代码作为输入，并产生所需的输出。我们将简单地接受 BrainFuck 代码为字符串，并通过解析字符串和检查每个字符的实际功能来生成输出。内存由一个字节类型的数组表示，该数组模拟从 0 到 65534 的最大 65535 位内存(65535 是可以用无符号 16 位二进制数表示的最高数字)。变量 ptr 指的是存储器阵列的当前索引。
在本文中，我们不会讨论用 BrainFuck 编写程序的细节。关于编写 BrainFuck 程序的更多细节，请参考以下链接:

*   [【脑子操(维基百科)](https://esolangs.org/wiki/Brainfuck)
*   [在 brain hook](https://www.geeksforgeeks.org/printing-geeks-geeks-brainfuck/)中打印“极客为极客”

示例:

```
Input : 
Output :  Hello World!

Input : 
Output : GEEKS FOR GEEKS
```

**大脑操解释器的 Java 实现-**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

class BrainFuck
{
    private static Scanner ob = new Scanner(System.in);
    private static int ptr; // Data pointer

    // Max memory limit. It is the highest number which
    // can be represented by an unsigned 16-bit binary
    // number. Many computer programming environments
    // beside brainfuck may have predefined
    // constant values representing 65535.
    private static int length = 65535;

    // Array of byte type simulating memory of max
    // 65535 bits from 0 to 65534.
    private static byte memory[] = new byte[length];

    // Interpreter function which accepts the code
    // a string parameter
    private static void interpret(String s)
    {
        int c = 0;

        // Parsing through each character of the code
        for (int i = 0; i < s.length(); i++)
        {
            // BrainFuck is a tiny language with only
            // eight instructions. In this loop we check 
            // and execute all those eight instructions

            // > moves the pointer to the right
            if (s.charAt(i) == '>')
            {
                if (ptr == length - 1)//If memory is full
                    ptr = 0;//pointer is returned to zero
                else
                    ptr ++;
            }

            // < moves the pointer to the left
            else if (s.charAt(i) == '<')
            {
                if (ptr == 0) // If the pointer reaches zero

                    // pointer is returned to rightmost memory
                    // position
                    ptr = length - 1;
                else
                    ptr --;
            }

            // + increments the value of the memory
            // cell under the pointer
            else if (s.charAt(i) == '+')
                memory[ptr] ++;

            // - decrements the value of the memory cell
            // under the pointer
            else if (s.charAt(i) == '-')
                memory[ptr] --;

            // . outputs the character signified by the
            // cell at the pointer
            else if (s.charAt(i) == '.')
                System.out.print((char)(memory[ptr]));

            // , inputs a character and store it in the
            // cell at the pointer
            else if (s.charAt(i) == ',')
                memory[ptr] = (byte)(ob.next().charAt(0));

            // [ jumps past the matching ] if the cell
            // under the pointer is 0
            else if (s.charAt(i) == '[')
            {
                if (memory[ptr] == 0)
                {
                    i++;
                    while (c > 0 || s.charAt(i) != ']')
                    {
                        if (s.charAt(i) == '[')
                            c++;
                        else if (s.charAt(i) == ']')
                            c--;
                        i ++;
                    }
                }
            }

            // ] jumps back to the matching [ if the
            // cell under the pointer is nonzero
            else if (s.charAt(i) == ']')
            {
                if (memory[ptr] != 0)
                {
                    i --;
                    while (c > 0 || s.charAt(i) != '[')
                    {
                        if (s.charAt(i) == ']')
                            c ++;
                        else if (s.charAt(i) == '[')
                            c --;
                        i --;
                    }
                    i --;
                }
            }
        }
    }

    // Driver code
    public static void main(String args[])
    {
        System.out.println("Enter the code:");
        String code = ob.nextLine();
        System.out.println("Output:");
        interpret(code);
    }
}
```

输出 1:

```
Enter the code:
--[+++++++>-->+>+>+<<<->---.>--..>+.<<<.+>->>.+++[.<]
Output:
Hello World!
```

输出 2:

```
Enter the code:
++++++++++[>+++++++>++++++++>+++<+++.>++..<+.
Output:
GEEKS FOR GEEKS
```

本文由 **Soumik Rakshit** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。