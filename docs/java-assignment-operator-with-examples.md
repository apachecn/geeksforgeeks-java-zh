# Java 赋值运算符示例

> 原文:[https://www . geesforgeks . org/Java-赋值-运算符-带示例/](https://www.geeksforgeeks.org/java-assignment-operator-with-examples/)

[**运算符**](https://www.geeksforgeeks.org/operators-in-java/) 构成了任何编程语言的基本构件。Java 也提供了许多类型的运算符，可以根据执行各种计算和函数的需要来使用，包括逻辑、算术、关系等。它们根据提供的功能进行分类。

**运算符类型:**

1.  [arithmetic operator](https://www.geeksforgeeks.org/java-arithmetic-operators-with-examples/)
2.  [Unary operator](https://www.geeksforgeeks.org/java-unary-operator-with-examples/)
3.  [Assignment operator](https://www.geeksforgeeks.org/java-assignment-operator-with-examples/)
4.  [relational operator](https://www.geeksforgeeks.org/java-relational-operators-with-examples/)
5.  [Logical operator](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)
6.  [ternary operator](https://www.geeksforgeeks.org/java-ternary-operator-with-examples/)
7.  [bitwise operator](https://www.geeksforgeeks.org/bitwise-operators-in-java/)
8.  T32] Shift operator [T34

这篇文章解释了所有关于赋值操作符的知识。

### 赋值运算符

这些运算符用于给变量赋值。赋值运算符的左侧操作数是一个变量，赋值运算符的右侧操作数是一个值。右侧的值必须与左侧的操作数具有相同的数据类型。否则，编译器将引发错误。这意味着赋值运算符具有从右到左的关联性，即运算符右侧给出的值被赋值给左侧的变量。因此，右侧的值必须在使用之前声明，或者应该是一个常数。赋值运算符的一般格式是，

```java
variable *operator* value;
```

#### Java 中赋值运算符的类型

赋值运算符通常有两种类型。它们是:

**1。简单赋值运算符:**简单赋值运算符与“=”符号一起使用，其中左侧由操作数组成，右侧由值组成。右侧的值必须与左侧定义的数据类型相同。

**2。复合赋值运算符:**复合运算符用于+、-、*、/与=运算符一起使用的情况。

让我们看看每个赋值运算符及其操作方式:

#### 1.(=)运算符:

这是最简单的赋值运算符，用于将右边的值赋给左边的变量。这是赋值运算符及其功能的基本定义。

**语法:**

```java
num1 = num2;
```

**示例:**

```java
a = 10;
ch = 'y';
```

## Java

```java
// Java code to illustrate "=" operator

import java.io.*;

class Assignment {
    public static void main(String[] args)
    {
        // Declaring variables
        int num;
        String name;

        // Assigning values
        num = 10;
        name = "GeeksforGeeks";

        // Displaying the assigned values
        System.out.println("num is assigned: " + num);
        System.out.println("name is assigned: " + name);
    }
}
```

**输出**

```java
num is assigned: 10
name is assigned: GeeksforGeeks
```