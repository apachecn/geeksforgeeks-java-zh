# Java 中的按位运算符

> 原文:[https://www.geeksforgeeks.org/bitwise-operators-in-java/](https://www.geeksforgeeks.org/bitwise-operators-in-java/)

**运算符**构成了任何编程语言的基本构件。Java 也提供了许多类型的运算符，可以根据执行各种计算和函数的需要来使用，包括逻辑、算术、关系等。它们根据提供的功能进行分类。以下是几种类型:

1.  [算术运算符](https://www.geeksforgeeks.org/java-arithmetic-operators-with-examples/)
2.  [一元运算符](https://www.geeksforgeeks.org/java-unary-operator-with-examples/)
3.  [赋值运算符](https://www.geeksforgeeks.org/java-assignment-operator-with-examples/)
4.  [关系运算符](https://www.geeksforgeeks.org/java-relational-operators-with-examples/)
5.  [逻辑运算符](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)
6.  [三元运算符](https://www.geeksforgeeks.org/java-ternary-operator-with-examples/)
7.  按位运算符
8.  [轮班操作员](https://www.geeksforgeeks.org/shift-operator-in-java/?ref=gcse)

本文解释了关于按位运算符需要了解的所有内容。

### 按位运算符

按位运算符用于对数字的各个位进行操作。它们可以与任何整型(char、short、int 等)一起使用。).它们在执行二进制索引树的更新和查询操作时使用。

现在让我们看看 Java 中的每一个按位运算符:

**1。按位或(|)**

该运算符是二元运算符，用“|”表示。它逐位返回输入值的或，即如果任一位为 1，则给出 1，否则显示 0。

**示例:**

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise OR Operation of 5 and 7
  0101
| 0111
 ________
  0111  = 7 (In decimal) 
```

**2。按位“与”(& )**

该运算符是二元运算符，用“& .”表示它逐位返回输入值的“与”，即如果两位都是 1，它给出 1，否则显示 0。

**示例:**

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise AND Operation of 5 and 7
  0101
& 0111
 ________
  0101  = 5 (In decimal) 
```

**3。按位异或(^)**

这个运算符是二元运算符，用'^.'表示它返回输入值的逐位异或，即如果对应的位不同，它给出 1，否则显示 0。

**示例:**

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise XOR Operation of 5 and 7
  0101
^ 0111
 ________
  0010  = 2 (In decimal) 
```

**4。按位补码(~)**

此运算符是一元运算符，用“~ .”表示它返回输入值的补码表示，即所有位反转，这意味着它每 0 到 1，每 1 到 0。

**示例:**

```
a = 5 = 0101 (In Binary)

Bitwise Complement Operation of 5

~ 0101
 ________
  1010  = 10 (In decimal) 
```

> **注意:**编译器会给出该数的 2 的补码，即 2 的 10 的补码为-6。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// bitwise operators

public class operators {
    public static void main(String[] args)
    {
        // Initial values
        int a = 5;
        int b = 7;

        // bitwise and
        // 0101 & 0111=0101 = 5
        System.out.println("a&b = " + (a & b));

        // bitwise or
        // 0101 | 0111=0111 = 7
        System.out.println("a|b = " + (a | b));

        // bitwise xor
        // 0101 ^ 0111=0010 = 2
        System.out.println("a^b = " + (a ^ b));

        // bitwise not
        // ~0101=1010
        // will give 2's complement of 1010 = -6
        System.out.println("~a = " + ~a);

        // can also be combined with
        // assignment operator to provide shorthand
        // assignment
        // a=a&b
        a &= b;
        System.out.println("a= " + a);
    }
}
```

**Output**

```
a&b = 5
a|b = 7
a^b = 2
~a = -6
a= 5
```

**移位运算符(移位运算符)**

移位运算符用于向左或向右移位一个数的位，从而分别将该数乘以或除以二。当我们必须将一个数乘以或除以 2 时，它们可以被使用。

**语法:**

```
 number shift_op number_of_places_to_shift;
```

**轮班操作员的类型:**

移位运算符进一步分为 4 种类型。这些是:

1.  有符号右移运算符(>>)
2.  无符号右移运算符(>>>)
3.  左移操作符
4.  无符号左移位运算符(<<

> **注:**关于 Java 中的移位运算符的更多细节，请参考 Java 中的[移位运算符](https://www.geeksforgeeks.org/shift-operator-in-java/)。